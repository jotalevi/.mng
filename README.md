
# .mng

`.mng` is a lightweight, efficient dotfile management tool for Arch-based systems. It provides an easy way to track, sync, and set up dotfiles across multiple machines using Git.

## Features

- **Track Specific Files**: Easily add or ignore files and directories to be tracked.
- **Sync Dotfiles**: Pull and apply changes across systems.
- **First-Time Setup**: Install dependencies, initialize files, and set up a Git repository for tracking.
- **Package Management**: Tracks installed packages in `packages.txt` for system consistency.

## Installation

### Prerequisites

Ensure that `yay` (AUR helper) is installed, or install it with:
```bash
git clone https://aur.archlinux.org/yay.git /tmp/yay && cd /tmp/yay
makepkg -si --noconfirm
```

### Install via AUR

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/jotalevi/.mng.git
   cd .mng
   ```

2. **Build and Install**:
   ```bash
   makepkg -si
   ```

Or, if already available on AUR:
```bash
yay -S dot-mng
```

### Manual Installation

1. Clone the repo and make the script executable:
   ```bash
   git clone https://github.com/jotalevi/.mng.git
   chmod +x .mng.sh
   ```

2. Move the script to a directory in your `$PATH` (e.g., `/usr/local/bin`):
   ```bash
   sudo mv .mng.sh /usr/local/bin/.mng
   ```

## Usage

`.mng` provides a series of commands to manage and sync your dotfiles.

```bash
.mng [option]
```

### Commands

- **`-setup`**: Initializes `.mng` for first-time setup on a new system. Prompts for a Git repository URL to clone and begin tracking dotfiles.
  
  ```bash
  .mng -setup
  ```

- **`-up`**: Syncs any tracked changes from your home directory to the dotfiles repository and updates `packages.txt`.
  
  ```bash
  .mng -up
  ```

- **`-r`**: Pulls the latest changes from the remote repository and applies them to your home directory.
  
  ```bash
  .mng -r
  ```

- **`-add <file_or_dir>`**: Adds specific files or directories to be tracked in `.mng`. Updates `.track` file to list items explicitly for tracking.
  
  ```bash
  .mng -add ~/.config/hypr
  ```

- **`-ignore <file_or_dir>`**: Removes specific files or directories from tracking. Updates `.track` to ignore specified items.
  
  ```bash
  .mng -ignore ~/.config/hypr
  ```

- **`-clone`**: Sets up `.mng` on a new machine by pulling and applying tracked files and directories from the repository.
  
  ```bash
  .mng -clone
  ```

## Configuration Files

- **`.track`**: Lists files and directories to be tracked. Update this file to explicitly specify which dotfiles `.mng` should sync.
- **`packages.txt`**: Lists all installed packages for system consistency across machines.

## Example Workflow

1. **Initialize `.mng`**:
   ```bash
   .mng -setup
   ```

2. **Add Files to Track**:
   ```bash
   .mng -add ~/.bashrc ~/.config/hypr
   ```

3. **Sync Changes**:
   ```bash
   .mng -up
   ```

4. **Apply Changes on Another Machine**:
   ```bash
   .mng -clone
   ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to open issues or submit pull requests for improvements or bug fixes.
