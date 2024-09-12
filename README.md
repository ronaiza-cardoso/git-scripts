### Git Scripts

The gscripts utility simplifies common Git operations for terminal enthusiasts.

## Installation

1. **Save the Script**

   Clone this repo to your chosen location, such as `~/git-scripts`:

 2. **Make the Script Executable**

       Open your terminal and run the following command to make the script executable:
    
       ```bash
       chmod +x ~/git-scripts
       ```


   3. **Add the following line to your shell configuration file (e.g., .bashrc, .zshrc):**

       If you want to run the gpull script from any directory without specifying the full path, you can add `~/git-scripts` to your PATH environment variable.
       
       ```bash
       export PATH="$HOME/git-scripts:$PATH"
       ```

        Reload your shell configuration with:

       ```bash
       source ~/.bashrc   # or source ~/.zshrc
       ```

### Usage

To use the gpull script, navigate to your Git repository and run:

```bash
gpull
```

This will execute the script, fetch the latest changes from the remote repository, and rebase your current branch on top of those changes.

## Troubleshooting
