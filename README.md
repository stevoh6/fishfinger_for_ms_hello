# How to ENABLE fingerprint sig-in
By default, PCs joined to a domain cannot sign in using a PIN unless enabled via policy. This tutorial will show you
how to enable or disable allowing domain users to set up and sign in to Windows 10 (version 1607) using a PIN.

You must be signed in as an **administrator** to enable or disable PIN for domain users.

### What is included:

`Allow_fingerprint.reg` >  regedit file for unlock adding MS Hello PIN and setup FingerPrint

`Revert_fingerprint.reg` > regedit file for revert changes

`README.md` > this tutorial

`Ms_pin_finger_setup.png` and `Ms_diag_blabla.png` > pictures for help


## SETUP:
1. Download latest release from: https://github.com/stevoh6/fishfinger_for_ms_hello/releases
2. Disconnect pc from domain network.
3.  Run `Allow_fingerprint.reg` as admin
4.  Manual steps:
    - Click on Accounts.
    - Open Settings.
    - Click on Sign-in options.
    - Click `Add PIN` under PIN section and setup **secure** PIN (picture `Ms_pin_finger_setup.png` step 1.)
    - Click `Setup` under Fingerprint section. (picture `Ms_pin_finger_setup.png` step 2.)
    - Close annoying MS windows dialog box. (picture `Ms_diag_blabla.png`)
    > **Important** PIN should be secure at least as domain password!
5. Test.
6. Done. You can connect to domain network.
7. (Optional) Restart pc.

## REVERT:
1. Run `Revert_fingerprint.reg` as admin
2. Manual steps:
    - Open Settings.
    - Click on Accounts.
    - Click on Sign-in options.
    - Under PIN section, click `Remove`.
        > More info why this needs to be manual change:
        https://www.slashadmin.co.uk/how-to-disable-pin-requirements-when-joining-windows-10-pc-to-azure-ad-and-using-office365-business-premium/ ,
        https://www.top-password.com/blog/disable-pin-login-in-windows-10-8/ ,
        https://superuser.com/questions/1279400/unable-to-set-or-remove-a-login-pin-on-windows-10
3. Done.
6. (Optional) Restart pc.

#### For more details, check some useful articles:
- https://www.top-password.com/blog/change-pin-complexity-requirements-policy-in-windows-10/
- https://social.technet.microsoft.com/Forums/en-US/5c9d5ed5-877f-4bba-b5be-3be1b97580d3/windows-hello-pin-signin-option-disabling?forum=win10itprogeneral
- https://superuser.com/questions/1322150/how-do-i-disable-windows-10-login-prompt-to-set-up-a-pin/1326422
- https://www.tenforums.com/tutorials/80520-enable-disable-domain-users-sign-pin-windows-10-a.html
- https://docs.microsoft.com/en-us/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password
- https://blogs.technet.microsoft.com/ash/2016/08/13/changes-to-convenience-pin-and-thus-windows-hello-behaviour-in-windows-10-version-1607/
