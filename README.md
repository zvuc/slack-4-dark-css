# 🌑 Slack 4.0+ Dark Mode CSS
**Dark mode css stylesheet for Slack desktop app (4.0.1+)**

![screenshot](https://user-images.githubusercontent.com/2870726/62346972-11e9b800-b533-11e9-81fc-3d51dc9aa2e7.png)

Reverse-engineers the Slack for Desktop CSS file to convert all instances of colors used to variables, then inverse graytones to work as "dark mode", then applying human-revised changes for optimal design and usability.

I made it from scratch because none of the existing dark-mode css files coming along with existing dark-mode patchers met my quality standards of being usable (no loose ends)

Currently at about 95% coverage for UIs. Still improving bits and pieces here and there where it may look weird. (borders being too dark and stuff)

If you see any critical issues (such as text inputs backgrounds being white and text being not visible) please file an issue to let me know and I'll try to fix asap.

## Disclaimer
This project is not affiliated with Slack at all. This is a hobby project therefore development may halt at any given point—especially if Slack finally starts to officially ship dark mode option in their Desktop app.

## How to apply style
### Patching Desktop app
[Slack Dark Mode by LanikSJ](https://github.com/LanikSJ/slack-dark-mode)

So far this is the only method that works on latest version (4.0+). Follow instructions in the repository readme.
Replace the `dark-theme.css` file with the one provided in this (slack-4-dark-css) repository.

### Using in browser
Use your favorite userstyle extension on your browser to override default stylesheet. Create a new userstyle to target your Slack app domain (https://app.slack.com/), then copy-paste the CSS file contents to apply.

## Development notes
### Gray color scheme generated from
https://www.colorbox.io/#steps=15#hue_start=292#hue_end=293#hue_curve=linear#sat_start=0#sat_end=0#sat_curve=linear#sat_rate=76#lum_start=99#lum_end=10#lum_curve=easeInOutCubic#minor_steps_map=50,80

### Compile stylesheet using LESS
```
npm install -g less
lessc dark-theme.less dark-theme.css
```


