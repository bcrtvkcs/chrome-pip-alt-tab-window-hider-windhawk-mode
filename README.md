# Chrome PiP Alt+Tab Window Hider

Removes Chrome Picture-in-Picture windows from the Alt+Tab switcher and Win+Tab,
while keeping them fully functional (always-on-top, playback controls, etc.).

## How it works
Chrome PiP windows are identified by three concurrent traits:
- Window class: `Chrome_WidgetWin_1`
- Extended style: `WS_EX_TOPMOST` set
- No owner window
- Size smaller than 50% of the primary monitor in both dimensions

When a matching window is found, `WS_EX_TOOLWINDOW` is added and
`WS_EX_APPWINDOW` is removed — the standard Win32 technique for hiding
a window from Alt+Tab and the taskbar.

## Compatibility
- Windows 10 and Windows 11
- Targets `chrome.exe` only
