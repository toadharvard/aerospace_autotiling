# AeroSpace autotiling script

The script analyzes window dimensions and chooses split direction based on aspect ratio (similar to Sway/i3 autotiling algorithm)

These two options have to be set to false inside your .aerospace.toml configuration file

    enable-normalization-flatten-containers = false
    enable-normalization-opposite-for-nested-containers = false

**Important:** You need to grant Accessibility permissions to your terminal in System Settings → Privacy & Security → Accessibility

You also need to trigger the script each time focus changes (this happens when a new window is opened as well)

    on-focus-changed = ['exec-and-forget /absolute/path/to/autotiling']

You can move the autotiling script to some directory, and then you need to add it in the .aerospace.toml configuration file inside on-focus-changed trigger

e.g.

    mv autotiling $HOME/.local/bin

You may need to add execute permission to the autotiling script

    chmod +x autotiling

Then the absolute path would be:

    on-focus-changed = ['exec-and-forget $HOME/.local/bin/autotiling']

Optional: You can filter by workspace names:

    on-focus-changed = ['exec-and-forget $HOME/.local/bin/autotiling W1 W2 W3']

Enjoy autotiling!

---
This project is licensed under the terms of the __MIT__ license.
