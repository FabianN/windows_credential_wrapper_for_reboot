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
The needed files can be found in the "Distribute" folder. First install vcredist_2010_x64.exe to the system. Then copy the dll to System32. To activate the credential wrapper run the Register.reg file on the system.

To hide the unwrapped credential provider add a group policy within "Computer Configuration->Administrative Templates->System->Logon", edit "Exclude credential providers", and add the following CLSID: {6f45dc1e-5384-457a-bc13-2cd81b0d28ed}

How to Uninstall
--------------------------------

To disable this credential wrapper you need to do two things.

FIRST remove the filter for the Windows credential provider. To do that go into Group Policy within "Computer Configuration->Administrative Templates->System->Logon", edit "Exclude credential providers", and remove the following CLSID: {6f45dc1e-5384-457a-bc13-2cd81b0d28ed}


Next, to remove the wrapped credential, remove these registry entries:
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Authentication\Credential Providers\{ACFC407B-266C-4085-8DAE-F3E276336E4B}
HKEY_CLASSES_ROOT\CLSID\{ACFC407B-266C-4085-8DAE-F3E276336E4B}

DO NOT remove the wrapped credential without removing the filter that filter's out the default windows credential provider, or you may get the machine in a state without any login prompt. You can remove the credential provider filter to have both, the wrapped and unwrapped credential provider side-by-side.