# [Racing Data Converter ![GitHub](https://img.shields.io/badge/GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/DallasFormulaRacing/Testing-Data-Converter)

## Basic information

---

### PM info
* Name - Andrew K.
* GitHub - `@aklundt`

### Contributors
<a href = "https://github.com/DallasFormulaRacing/Testing-Data-Converter/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=dallasformularacing/Testing-Data-Converter" width="3%">
</a>

### Description
Racing Data Converter is a Python library for converting CAN bus telemetry data into Motec LD files, compatible with Motec i2 Pro data analysis software. The core functionality of this project is provided by three key modules:

* `interpolate_channels.py` – Resamples and interpolates raw channel data to a consistent timeline.
* `transform_channel.py` – Applies predefined transforms (unit conversions, offsets, scaling) to individual data channels.
* `mandrewLDWriter.py` – Third-party utility for encoding and writing Motec LD file structures.

The `example_use.py` script demonstrates how to integrate these modules into a complete conversion workflow.

!!! note "Legacy module"
    The `data_deserializer.py` and `quick_decoder.py` modules were originally developed for proof-of-concept work and are not actively maintained in this repository. They are **not required** for the primary conversion workflow.

## Working with the source

### Dependencies

* Python 3.9 or higher.
* `pandas` for data handling.
* CAN-to-CSV conversion tool:
    * community `cantools` package (or similar).
    * Legacy (unmaintained) `data_deserializer.py` module for proof-of-concept functionality.

### Installation

1. Clone the repository:

   ```sh
   git clone https://github.com/DallasFormulaRacing/Testing-Data-Converter.git
   ```
2. Change into the project directory:

   ```sh
   cd Testing-Data-Converter
   ```
3. (Optional) Create and activate a Python virtual environment:

   ```sh
   python3 -m venv venv
   source venv/bin/activate
   ```
4. Install required Python packages:

   ```sh
   pip install pandas cantools
   ```

### Usage

Below is a simplified, annotated example following the structure of `example_use.py`. Copy these steps into your own scripts and adjust paths, metadata, and channel definitions as needed.

```py
import time
import pandas as pd
from channels_to_motec.mandrewLDWriter import File, Channel
import channels_to_motec.transform_channel as tc

# 1. Load raw CAN data (CSV) into a DataFrame
df = pd.read_csv('Data/Converted CANbus Data/session.csv')

# 2. Define the list of channels to include
#    Each tuple: (Full Name, Short Name, Unit, Data column in df, optional transform function)
channels_info = [
    ('Engine RPM',      'RPM',  'rpm', 'RPM',                   None),
    ('Brake Pres Front','BPF',  'psi', 'Analog Input #6',       tc.transform_brakes_pressure),
    ('Steered Angle',   'SA',   'deg', 'Analog Input #2',       tc.transform_steered_angle),
    # …add other channels as needed, matching names in the DataFrame
]

# 3. Create and configure the MoTeC file object
motec = File()
motec.Time = time.localtime(df['timestamp'][0])
motec.Driver       = 'Driver Name'
motec.Vehicle      = 'Vehicle ID'
motec.Venue        = 'Track or Location'
motec.EventName    = 'Session Name'
# …set other metadata fields (ShortComment, EventSession, VehicleWeight, etc.)

# 4. Process each channel and add to the file
from channels_to_motec.example_use import process_channel  # helper from example_use.py
for name, short_name, unit, data_series_name, transform_function in channels_info:
    data, frequency = process_channel(df, 'timestamp', data_series_name, transform_function)
    channel = Channel(frequency, name, short_name, unit, data)
    motec.add_channels(channel)

# 5. Write the MoTeC LD file to disk
with open('output.ld', 'wb') as f:
    motec.write(f)
```

This flow matches the internal logic of `example_use.py`:

1. Load data with `pandas.read_csv`.
2. Define `channels_info` matching your DataFrame columns.
3. Initialize the MoTeC `File` and set metadata.
4. Loop over each channel, process with either a transform or `assimilate_channel`, then add to the file.
5. Write the final `.ld` file.


Use these steps as a blueprint for integrating Racing Data Converter into your own applications.
