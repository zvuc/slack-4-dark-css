> ### 🎊🎉 The End Is Here 🎊🎉
> On September 13, 2019 (or some time near depending on your timezone) Slack finally launched official dark mode support for browser and desktop clients. (https://twitter.com/SlackHQ/status/1172165133956603904) You can change the settings now in-app, from Themes in Preferences. Thanks Slack!

---

> ### ~⚠️ Almost-end-of-life notice:~
> ~As of August 23, 2019 (or some time near), Slack seems to have updated their stylesheet to use CSS variables in colors instead of using static ones, perhaps as if to lay out the foundation for themable 'dark mode' support. I've also found that they already include an alternative color palette for dark theme! Which essentially brings official support for dark mode for desktop and web—just not announced for public yet.~
> ~So until that day finally comes, this theme will continue to exist but in a much more simplified form, where we just enable the dark theme color palette. Also keeps some little overrides for some parts that seemingly are still WIP darkification by Slack team.~

---

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

### Step-by-step instructions for non-developers (macOS):
1. Make sure to have a clean installation of Slack from App Store (Open Slack > About Slack > check `Version 4.0.1 (App Store)`)
1. Download patcher ZIP file by [LanikSJ](https://github.com/LanikSJ/slack-dark-mode), extract to desktop - [Download](https://github.com/LanikSJ/slack-dark-mode/archive/master.zip)
1. Download latest CSS file and save to Desktop/slack-dark-mode (overwrite existing file) - [Download](https://raw.githubusercontent.com/zvuc/slack-4-dark-css/master/dark-theme.css) 
1. Open Terminal.app
1. Install Xcode command line tools - `xcode-select --install`
1. Install nvm - `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash`
1. Reload terminal - `source ~/.bash_profile`
1. Install node - `nvm install stable`
1. Navigate to folder in terminal - `cd ~/Desktop/slack-dark-mode`
1. Edit permissions for script to run - `chmod +x ./slack-dark-mode.sh`
1. Run patcher script -  `./slack-dark-mode.sh`
1. Refresh Slack app (Cmd+R) or restart

If there is an easier way to patch stylesheet without having to install all the developer dependencies (NodeJS), please let me know.

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


