[中文](/README.md)

## PuTTYAttach Introduction

PuTTYAttach has been packaged and released, and it can be used by simply extracting the files.[release](https://github.com/hfcjx/PuTTYAttach/releases/tag/V1.0)

## What is PuTTYAttach?

PuTTYAttach is a Windows program, specifically designed for the Microsoft® Windows® platform.

PuTTYAttach is used for organizing PuTTY sessions and displaying multiple PuTTY connections in tabs. It supports file transfers using the XModem, YModem, and ZModem protocols, automatic username and password input, as well as the automated sending of preset command sequences.

For a more detailed introduction, please refer to the [help document](/help-en.md) .

## Technical Features

- **Session Organization:** Sessions are listed and can be managed hierarchically.
- **Embedded PuTTY.exe:** You can create, modify, and save PuTTY sessions within the same window.
- **Multi-tab Interface:** The connected sessions are displayed in tabs, which can show either the session name or an alias.
- **Automatic Login:** Supports auto-sending of usernames and passwords for automatic login.
- **Automated Command Execution:** Sends preset command sequences automatically upon login.
- ★**Integration with lrzsz:** Supports XModem, YModem, and ZModem file transfer protocols.
- ★**Monitor Remote lrzsz Commands:** Detects lrzsz commands input on the remote server and automatically triggers the local lrzsz to complete file transfers.
- ★**Auto initiate Local lrzsz:** Starts the local lrzsz and automatically sends lrzsz commands to the remote server for file transfer.
- ★**Script Execution:** Allows the execution of custom scripts.

**Note:**

★ Requires [pipPuTTYcn](https://github.com/hfcjx/pipPuTTYcn) or [pipPuTTYen](https://github.com/hfcjx/pipPuTTYen) for full functionality.



## Why PuTTYAttach?

There is a device with a simple serial shell server that supports the YModem protocol for uploading and downloading files. Using the free version of XShell for interaction has been working perfectly fine.

Now, the device needs to add TCP/IP connectivity. The shell server must support both serial and TCP-Raw connections, but XShell does not support TCP-Raw, so another shell tool is needed.

SecureCRT supports both serial and TCP-Raw connections, as well as YModem file transfer, and works perfectly for interactions. However, SecureCRT is not free software.

PuTTY is known as one of the best telnet/SSH clients, supporting both serial and TCP-Raw connections, and is open-source and free. However, it does not natively support the YModem protocol.

By chance, I discovered the open-source software lrzsz, which supports the XModem, YModem, and ZModem protocols and perfectly handles YModem transfers.

This led to the idea of developing a bridge software to integrate PuTTY with lrzsz, enabling file transfers using XModem, YModem, and ZModem protocols. Later, I also added PuTTY session management and a multi-tab interface, resulting in the creation of **PuTTYAttach**.

## pipPuTTY

**pipPuTTY** is a branch of PuTTY version 0.81. It can be used independently or work with PuTTYAttach.

PuTTYAttach acts as a bridge between PuTTY and lrzsz. To exchange data with PuTTY, the original PuTTY code must be modified. This modification is what pipPuTTY accomplishes.

PuTTYAttach redirects the standard input and output of pipPuTTY. `stdin` is used to send data to PuTTY, `stderr` is used to receive terminal data, and `stdout` is used to receive file data.

Alternatively, data can be exchanged using the **WM_COPYDATA** message, and some features use this method.

This approach allows PuTTYAttach to work with PuTTY without changing the original PuTTY code structure. The changes to the code are minimized, with function calls added to work with PuTTYAttach.

**PuTTYAttach** can also work with the original version of PuTTY, though some features will be unavailable.

| **Feature**                         | **Original PuTTY** | **pipPuTTY** |
| ----------------------------------- | ------------------ | ------------ |
| Session Management                  | ●                  | ●            |
| Multi-tab Interface                 | ●                  | ●            |
| Auto Authentication (Prompt)        |                    | ●            |
| Auto Authentication (Delay)         | ●                  | ●            |
| Auto Send Command Sequence (Expect) |                    | ●            |
| Auto Send Command Sequence (Delay)  | ●                  | ●            |
| Scripting                           |                    | ●            |
| File Transfer (XYZModem)            |                    | ●            |

## lrzsz-pip

**[lrzsz-pip](https://github.com/hfcjx/lrzsz-pip)** is a branch of **[lrzsz](https://github.com/trzsz/lrzsz-win32)**.

**Main Modifications**: It unifies the debug information format for XModem, YModem, and ZModem protocols to make it easier for PuTTYAttach to parse the status of the file transfer process.

PuTTYAttach, in combination with **[lrzsz-pip](https://github.com/hfcjx/lrzsz-pip)** and **[lrzsz](https://github.com/trzsz/lrzsz-win32)**, is capable of completing file transfers.

Using **lrzsz-pip** provides more complete and comprehensive data during the file transfer process.
