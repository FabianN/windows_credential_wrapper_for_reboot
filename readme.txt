//
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF
// ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO
// THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A
// PARTICULAR PURPOSE.
//
// Copyright (c) Microsoft Corporation. All rights reserved.
//

Overview
--------
This is a wrapped credential that provides a command link below the password text box that allows the user to reboot the machine, built off of the provided credential wrapper sample from Microsoft.

How to Install
--------------------------------
The needed files can be found in the "Distrubute" folder. First install vcredist_2010_x64.exe to the system. Then copy the dll to System32. To activate the credential wrapper run the Register.reg file on the system.

To hide the unwrapped credential provider add a group policy within "Computer Configuration->Administrative Templates->System->Logon", edit "Exclude credential providers", and add the following CLSID: {6f45dc1e-5384-457a-bc13-2cd81b0d28ed}
