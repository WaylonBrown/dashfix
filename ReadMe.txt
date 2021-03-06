DashFix (OpenVR DashBoard Fixer) v1.0
-------------------------------------

Inputs from connected game controllers can interfere with OpenVR Dashboard
pointer navigation. The problem manifests itself as the inability to click
buttons and other elements in the dashboard user interface.

Steering wheels and HOTAS devices are usually the cause, as they often have a
rest position with a non-zero axis value, which the dashboard continually acts
upon. It's inconvenient to disconnect them during dashboard use, and there's
currently no way to tell Steam to ignore them.

DashFix lets you ignore the unwanted inputs, and use the dashboard normally.


USAGE

- connect your game controllers
- launch DashFix.exe
- uncheck any controllers you don't want to use with the dashboard
- optionally, select to have DashFix run on every Windows startup
- click OK

DashFix can be started before or after Steam, and re-run to change controller
selection. Don't worry, ignored controllers still work as normal in all other
games and applications.


IMPLEMENTATION

DashFix injects a DLL into Steam.exe and vrdashboard.exe, hooking calls to
SDL_GetJoystickAxis so they return zero for some controllers. This process
injection technique could upset some runtime virus scanners.

Please let me know if you have any problems, or find other places where
controllers are interfering with normal use.


CHANGELOG

v1.0
- added individual controller selection
- added optional launch on Windows startup
- improved pre-hook checks and error handling
- added MIT license

v0.1
- first public test release, blocking all controllers

---

Simon Owen
https://github.com/simonowen/dashfix
