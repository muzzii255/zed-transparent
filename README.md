# Zed Custom Themes Installation Guide for Linux

This guide will walk you through installing custom themes in Zed editor on Linux systems.

## Prerequisites

- Zed editor installed on your Linux system
- Basic familiarity with terminal/command line
- A custom theme JSON file (like the One Dark Transparent Catppuccin theme)

## Installation Methods

### Method 1: Using Zed's Themes Directory (Recommended)

1. **Create the themes directory** (if it doesn't exist):
   ```bash
   mkdir -p ~/.config/zed/themes
   ```

2. **Save your theme file** in the themes directory:
   ```bash
   # Save as: ~/.config/zed/themes/Your-Theme-Name.json
   # The filename should match the theme name you want to use
   ```

3. **Update your settings.json** to use the theme:
   ```bash
   nano ~/.config/zed/settings.json
   ```
   
   Add or modify the theme section:
   ```json
   {
     "theme": {
       "mode": "system",
       "light": "One Dark",
       "dark": "Your-Theme-Name"
     }
   }
   ```

4. **Restart Zed** - the theme will be automatically detected and loaded!

### Method 2: Direct Theme Selection (Alternative)

If you prefer to select themes manually:

1. **Install theme** using Method 1 above
2. **Use command palette**:
   - Press `Ctrl+Shift+P` 
   - Type "theme" and select "zed: select theme"
   - Choose your theme from the list

### Method 3: Inline Theme Definition (Advanced)

For embedding themes directly in settings.json:

1. **Open your Zed config directory**:
   ```bash
   cd ~/.config/zed
   ```

2. **Edit the settings.json file**:
   ```bash
   nano settings.json
   # or use your preferred editor
   code settings.json
   vim settings.json
   ```

3. **Add your theme** to the configuration:
   ```json
   {
     "theme": "One Dark Transparent Catppuccin",
     "themes": {
       // Your theme content goes here
     }
   }
   ```

## Quick Setup Example

Based on your configuration style, here's the simplest way:

1. **Save theme file**:
   ```bash
   # Save the theme JSON as:
   ~/.config/zed/themes/Transparent Catppuccin Dark.json
   ```

2. **Update settings.json**:
   ```json
   {
     "theme": {
       "mode": "system",
       "light": "One Dark", 
       "dark": "Transparent Catppuccin Dark"
     }
   }
   ```

3. **Restart Zed** - Done! 🎉

**Note**: The theme name in your settings.json should match either:
- The filename (without .json extension), OR
- The "name" field inside the theme JSON file

**Zed configuration directory:**
```
~/.config/zed/
```

**Themes directory:**
```
~/.config/zed/themes/
```

**Main settings file:**
```
~/.config/zed/settings.json
```

## Theme File Structure

Your theme JSON file should follow this structure:

```json
{
  "name": "Theme Name",
  "author": "Author Name",
  "themes": [
    {
      "name": "Theme Name",
      "appearance": "dark",
      "style": {
        // Theme properties here
      }
    }
  ]
}
```

## Troubleshooting

### Theme Not Appearing

1. **Check file location**: Ensure the theme file is in the correct directory
2. **Verify JSON syntax**: Use a JSON validator to check for syntax errors
3. **Restart Zed**: Sometimes a full restart is needed
4. **Check file permissions**: Ensure Zed can read the theme file
   ```bash
   chmod 644 ~/.config/zed/themes/your-theme.json
   ```

### Transparency Not Working

1. **Check compositor**: Ensure your Linux desktop compositor supports transparency
2. **Verify theme values**: Look for transparency values like `#08090960` (with alpha channel)
3. **Desktop environment**: Some DEs may override transparency settings

### Colors Not Loading

1. **Validate theme structure**: Ensure all required fields are present
2. **Check color format**: Colors should be in hex format (`#rrggbb` or `#rrggbbaa`)
2. **Change Transparency**: Transparency can be changed by editing the alpha values of background colors
3. **Restart required**: Some theme changes require a Zed restart

## Tips

- **Backup your settings** before making changes
- **Test themes** in a separate Zed instance first
- **Use relative paths** when possible for portability
- **Check the Zed documentation** for the latest theme specification


**Verify installation:**
```bash
# List installed themes
ls ~/.config/zed/themes/

# Check settings
cat ~/.config/zed/settings.json
```

## Additional Resources

- [Zed Official Documentation](https://zed.dev/docs)
- [Zed Themes Repository](https://github.com/zed-industries/zed)
- [Theme Development Guide](https://zed.dev/docs/themes)

---

Happy theming! 🎨
