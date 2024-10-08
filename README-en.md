# GenshinArtifacter_Discrord-BOT

## About the end of development
The development of this BOT has been terminated. The repository will therefore be archived.

## What is this?

This is a code to make "ArtifacterImageGen", which calculates scores of relics of the Genshin Impact and generates images, available as a BOT for Discord.

We decided to distribute the code under the MIT license so that anyone can easily use the DiscordBOT created based on "ArtifacterImageGen".

This is thanks to "ArtifacterImageGen" being distributed under MIT license on github.

Our sincere thanks to Mr. Hyugo.

Also, the "EnkaNetworkAPI" library makes it easy to update assets.

My sincere thanks to yuko1101.

This is almost my first time using github, so there may be mistakes, etc.

I would appreciate it if you could contact me if you find any mistakes.

## operating environment

These are the versions that have been tested to work.

Using these versions may not work in some environments.

Python 3.9.2, 3.11.2, 3.12.1

Discord.py 2.2.2, 2.3.2

python-dotenv 1.0.0

Pillow 9.5.0, 10.0.1, 10.2.0

PyYAML 6.0, 6.0.1

requests 2.28.2, 2.31.0

Node.js 18.16.0, 20.10.0

npm 9.5.1, 10.3.0

## Getting Started

Run the `/help` command to see an explanation about the command.

## How to Setup

### be common

<details>
<summary>Click to open</summary>

#### Create Disocrd BOT

Access the DiscordDeveloperPortal.

https://discord.com/developers/applications

Click on "New Application."

(If you have already created a dedicated BOT, skip to token generation.)

Decide on a name for the BOT and enter it in the "NAME" field.

Agree to the Terms of Use and Developer Policy and click "Create".

Select the "BOT" tab under "SETTING" and click "Add Bot.

Click "Yes, do it!" when the confirmation dialog appears.

(If 2FA is set, please authenticate.)

#### Token Generation

Click on "Copy" under "TOKEN" to copy the BOT token.

Make a note (paste) of this token in a notepad, etc.

This token must not be seen by anyone.

#### Setting BOT

Turn ON "PRESENCE INTENT", "SERVER MEMBERS INTENT", and "MESSAGE CONTENT INTENT" in "Privileged Gateway Intents".

Remember to click "Save Changes" to save your changes.

#### Allow BOTs to join the server

Select "OAuth2" and "URL Generator" from the menu.

Check the "BOT" checkbox under "SCOPES" and set the "BOT PERMISSIONS" to the necessary permissions.

(If you own the server and trust the code of this BOT, you may check the "Administrator" checkbox.)

Copy the URL displayed in the "GENERATED URL" field and access the copied URL.

Select the server you want the BOT to join and click Yes.

Confirm that the authorization is correct and click authentication.

Clear the hCaptcha authorization and enlist the BOT.

This completes the preconfiguration of the Discord BOT.

#### Download Source
Download this repository from github as a zip file or clone it with GithubCLI, etc.

https://github.com/tarou-software/GenshinArtifacter_Discrord-BOT

(If you downloaded the file as a zip file, please unzip it.)

Open the file ".env" in the directory and replace "token here!" with the BOT token copied in "Token Generation".

#### Change the configuration

In the directory containing the BOT source code, there is a file called "config.json".

This file modifies the BOT configuration.

Open the file in a text editor, etc., **as some parts need to be changed before starting**.

```
"Administrator_Name" : "Please Enter Your Name",
```

Please change "Please Enter Your Name" to your nickname in the line "Please Enter Your Name".

This is a **necessary setting** to use the EnkaNetwork API, so be sure to **do** this.

Also,

```
"BOT_Ver" : ~~~,
```

Do not **change** the item.

<details>
<summary>Optional settings</summary>

##### uid_register

```
"uid_register" : true,
```

By changing this item, you can enable or disable UID registration.

Change to 

- "true" to enable
- "false" to disable

(The default setting is "true", which is enabled.)

##### image_uid_mode

```
"image_uid_mode" : true
```

By changing this item, you can avoid a situation where another person's image is sent depending on the timing.

Change to 

- "true" to enable
- "false" to disable

(The default setting is "true", which is enabled.)

</details>

</details>

### Windows

<details>
<summary>Click to open</summary>

Run the check version command to see if python is installed.

```
python --version
```

If the version is displayed, you are OK.

(If it is not installed, download and install the installer from the [official page](https://www.python.org/).)

Install each library using pip.

The command is as follows

Installs various libraries.
```
pip install discord.py
```

```
pip install python-dotenv
```

```
pip install Pillow
```

```
pip install pyyaml
```

```
pip install requests
```

Make sure everything is installed correctly.

(Be sure to install Pillow version 9.5.0 or higher, otherwise ArtifacterImageGen will not work. Example: 8.1.2 will not work)

#### Launch the BOT.

Launch Command Prompt, etc.

Change the current directory to the source directory.

Execute the following command.

```
python bot_start.py
```

(It is recommended to create a batch script file.)

Confirm that "Ready! Name:~~~" is displayed and the BOT is running successfully on Discord.

Translated with DeepL.com (free version)

</details>

### Linux(Debian or Ubuntu)

<details>
<summary>Click to open</summary>

#### Setup Python
Run the check version command to see if python is installed.

````
python3 --version
````

If the version is displayed, you are OK.

Install pip.

````
sudo apt update
sudo apt install python3-pip
```` 

Use PIP to install each library.

```
pip3 install discord.py
```

```
pip3 install python-dotenv
```

```
pip3 install Pillow
```

```
pip3 install pyyaml
```

```
pip3 install requests
```

Verify that everything was installed correctly.

(Pillow version must be 9.5.0 or higher, ArtifacterImageGen will not work. E.g. it does not work with 8.1.2).

#### Make the BOT work

Launch a command prompt or similar.

Change the current directory to the source directory.

Execute the following command

```
python3 bot_start.py
```

(It is recommended to create a batch file.)

"Ready! Name:~~" and confirm that the BOT is working properly on Discord.

</details>

## Asset Update

Due to the specifications of ArtifacterImageGen, it is necessary to update assets to accommodate new elements that are added when Genshin Impact is upgraded.

### Initial Setup

<details>
<summary>Optional settings</summary>

#### Installing Node.js

Install the LTS version of Node.js with the following command.

```
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt install nodejs -y
```

#### Library Installation

Change the current directory to the source directory.

Execute the following command.

```
npm install enka-network-api
```

</details>

### update

<details>
<summary>Optional settings</summary>

**IMPORTANT**
When updating, make sure that the EnkaNetwork is not under maintenance.

To update, change the current directory to the source directory and execute the following command.

```
node asset_update.js
```

(It is recommended to create a batch file.)

When run, it will automatically update character, weapon, and artifact assets.

It is not necessary to restart the BOT when updating.

</details>

## Copylight

"Genshin Impact" is registered trademarks or trademarks of 上海米哈游綱絡科技股分有限公司(miHoYo) and COGNOSPHERE.

ArtifacterImageGen Copyright (c) Hyugo(FuroBath) ([artifacterbot - Twitter](https://twitter.com/artifacterbot))

GenshinArtifacter_Discrord-BOT Copyright (c) mendoitarou_

EnkaNetworkAPI(Library) Copyright (c) yuko1101

## special thanks

[FuroBath/ArtifacterImageGen](https://github.com/FuroBath/ArtifacterImageGen)

[yuko1101/enka-network-api](https://github.com/yuko1101/enka-network-api)

## translation
This README-en.md has been translated from English to Japanese after some text has been translated from Japanese to English using the 'DeepL translation tool'.

https://www.deepl.com/ja/translator

## Contact

It may take some time for us to reply.

Please understand that it may take some time to reply.

**Due to the end of development, we are unable to reply to any enquiries about this BOT.**

**Please note that we cannot reply to inquiries about this BOT.**

Twitter: [@mendoitarou_](https://twitter.com/mendoitarou_)

E-Mail: [contact@mendoitarou.com](mailto:contact@mendoitarou.com)

## Release Notes

### 1.2.6.1

<details>
<summary>Click to open</summary>

- Exception handling added
- Some internal code optimisation

</details>

### 1.2.6

<details>
<summary>Click to open</summary>

- Fixed an issue where an error occurred during maintenance and exception handling was not working. A message is sent during maintenance.

</details>

### 1.2.5

<details>
<summary>Click to open</summary>

- Support for new player icon format
- Changed specification to cache API replies (recommended API behavior)

</details>

### 1.2.4

<details>
<summary>Click to open</summary>

- Added a command to generate an image by manually entering the UID.

</details>

### 1.2.3

<details>
<summary>Click to open</summary>

- Fixed problem with character consts not being applied.

</details>

### 1.2.2

<details>
<summary>Click to open</summary>

- Fixed a problem where an error occurred when trying to generate an image of a character not wearing a artifact and the image was not generated.

</details>

### 1.2.1

<details>
<summary>Click to open</summary>

- Changed the name of the command to see information about the BOT
- Added a command to view command descriptions.

</details>

### 1.2.0

<details>
<summary>Click to open</summary>

- Embedding color changes according to the element of the generated image character
- Asset update program added

</details>

### 1.1.0

<details>
<summary>Click to open</summary>

- Fixed a part that did not follow the API rules.
- Changed behavior when UID is not registered.
- Removed /build_no command due to changed behavior.
- Fixed a problem that images of different users may be generated depending on timing when generating images (can be turned on/off by configuration).
- Added explanation to README to reflect changes in operation.

</details>

### 1.0.0

<details>
<summary>Click to open</summary>

- Initial Release

</details>
