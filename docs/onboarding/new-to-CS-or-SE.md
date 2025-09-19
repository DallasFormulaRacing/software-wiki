# Introduction

Hey, seeing as you clicked this you presumably have little to no experience in the Computer Science or Software Engineering field, and that's totally okay. 

Here on the DFR Software team, very few people have any kind of background knowledge with most of the technologies that we utilize on a daily basis when they enter the club, and that's 100% normal. For most, any kind of formal education up until college lacks any form of "computer education," despite using them almost every day. So suffice to say, you're not alone. Hopefully with the help of this onboarding, and your own willingness to learn (this really is the most important thing you need), you'll be a contributing member of the team in no time!

## Before you get started

When it comes to learning any language or technology, I always recommend that you go ahead and give yourself an end goal of what you want to accomplish before starting anything. For example if you want to learn [Python](https://www.python.org/), then you could give yourself the goal of wanting to make your own local webserver. From that goal learning how to build it with your own research, or knowledge you carry from elsewhere, will allow you to learn how different parts of the [Python](https://www.python.org/) language interact, along with also actively learning how to problem solve. Instead of simply following a tutorial that tells you everything to do.


## Getting started

---

### Choosing an IDE

If you're truly brand new to programming at all, then you've likely never heard of what an Integrated Development Environment (IDE) is, and that's all good. 

When most CS/SE students come to UTD, they are presented with an online IDE like [OnlineGDB](https://www.onlinegdb.com/online_c++_compiler) through their classes, and while this does suit the needs of most class here on campus, there should never be a time when you rely on an online IDE for any kind of "large scale" development, or really ever... It's best practice to avoid using any online IDEs, primarily from a usability standpoint, but also because a local IDE, such as [VS Code](https://code.visualstudio.com/), has many more useful features when developing anything.

Something worth considering, is there is a **VAST** variety of IDEs, and not all of them are created equal. In essence this means that it's kind of personal preference as to what your favorite environment is, and as such below will be a list of the most commonly used IDEs for all kinds of development. (Note, there are many IDEs that are specialized in a specific language, or type of development, but for the sake of this write-up I will only be focusing on lightweight IDEs that work with "any" language.)

(Below is a list taken from [Awesome-IDEs](https://github.com/zeelsheladiya/Awesome-IDEs). I highly recommend checking this list out if you want a larger more specified list of IDEs.)

| Name | Description | Links | System Support | Fees |
| ---- | ----------------------------- | --- | --- | --- |
| <img src="https://raw.githubusercontent.com/zeelsheladiya/Awesome-IDEs/refs/heads/main/Resources/Icons/vscode.png" alt="icon" width=25 height=25> Visual Studio Code | A highly customizable code editor with a wide range of extensions for various languages and frameworks. | [Offical Website](https://code.visualstudio.com/) </br> [Guthub](https://github.com/microsoft/vscode) |  `Mac` `Windows` `Linux` `Online` `Chrome OS`| Free, Proprietary, Open-Source |
| <img src="https://raw.githubusercontent.com/zeelsheladiya/Awesome-IDEs/refs/heads/main/Resources/Icons/PyCharm.png" alt="icon" width=25 height=25> PyCharm | An intelligent Python IDE with integrated tools for efficient coding and debugging. | [Official Website](https://www.jetbrains.com/pycharm/) </br> [Github](https://github.com/JetBrains/intellij-community/tree/master/python)  | `Mac` `Windows` `Linux` | Paid, Proprietary, Freemium, Open-Source |
| <img src="https://raw.githubusercontent.com/zeelsheladiya/Awesome-IDEs/refs/heads/main/Resources/Icons/Eclipse.png" alt="icon" width=25 height=25> Eclipse | A versatile IDE is known for its Java development capabilities and extensive plugin ecosystem. | [Official Website](https://www.eclipse.org/) | `Mac` `Windows` `Linux` `BSD` | Paid, Proprietary, Freemium, Open-Source |
| <img src="https://raw.githubusercontent.com/zeelsheladiya/Awesome-IDEs/refs/heads/main/Resources/Icons/kdevelop.png" alt="icon" width=30 height=30> KDevelop | A cross-platform IDE for C, C++, Python, QML/JavaScript and PHP | [Official Website](https://apps.kde.org/kdevelop/) </br> [Github](https://github.com/KDE/kdevelop) | `Windows` `Linux` `KDE` | Free, Open-Source |
| <img src="https://raw.githubusercontent.com/zeelsheladiya/Awesome-IDEs/refs/heads/main/Resources/Icons/visual_studio.png" alt="icon" width=25 height=25> Microsoft Visual Studio | An integrated development environment for various programming languages, including C++, C#, and more. | [Official Website](https://visualstudio.microsoft.com/) | `Mac` `Windows` `Online` `.NET Framework` | Free, Paid, Proprietary |

My personal recommendation is [VS Code](https://code.visualstudio.com/) for it's versatility and how lightweight it is out of the box. On top of those factors it also has a **MASSIVE** plugin/extension community that likely has any and all means of solving any problem that you might run into while using [VS Code](https://code.visualstudio.com/), including also being one of the most customizable visually.

### Downloading and installing Python

As most, if not all, of the projects within DFR are based on [Python](https://www.python.org/), having it on your system is a very important step.

Most of the projects here are developed on [Python 3.10.X](https://www.python.org/downloads/release/python-31011/) and higher. This means that you will at the very least need some version of Python, greater than or equal to 3.10.X. 

The most up to date versions as of the time of writing, with installers, can be found in the list below.

|Version #|Date of Release|Version Download Page|
|:---:|:---:|:---:|
|3.13.7|August 14, 2025|[Download](https://www.python.org/downloads/release/python-3137/)|
|3.12.10|April 8, 2025|[Download](https://www.python.org/downloads/release/python-31210/)|
|3.11.9|April 2, 2024|[Download](https://www.python.org/downloads/release/python-3119/)|
|3.10.11|April 5, 2023|[Download](https://www.python.org/downloads/release/python-31011/)|

Once you have selected a version, find the installer for your specific operating system, in most cases this will be the `Windows installer (64-bit)`.

Again assuming you are on a Windows operating system, open the installer with administrative permissions, and once open make sure to tick the `Add python.exe to PATH` check box at the bottom of the installer before clicking "Install Now".

After the installer completes, you can check if you have [Python](https://www.python.org/) available by opening your terminal of choice and typing the command `python --version`, at which point you should see the console display a string of text that states your installed [Python](https://www.python.org/) version (If on Windows you can open your terminal by pressing your Windows key + R, then within the box that appears typing `cmd` and clicking `OK`.)

## What now?

After you have selected an IDE, and successfully installed [Python](https://www.python.org/), you're good to continue onto where everyone else would start! You can do this by checking the sidebar, or just by clicking the "Next" arrow right below this.