### gpull Script

The gpull script is a simple utility for performing a git pull operation with rebase for the current branch in a Git repository. This script automates fetching the current branch name and rebasing it on top of the latest changes from the remote repository.

## Installation

1. **Save the Script**

   Save the following script as gpull in your desired location, for example, `~/scripts`:

   ```bash
   #!/bin/bash

   # Get the current branch name
   branchname=$(git rev-parse --abbrev-ref HEAD)
   if [ -z "$branchname" ]; then
       echo "Error: Unable to determine branch name."
       exit 1
   fi

   # Pull with rebase
   git pull --rebase origin "$branchname"
   if [ $? -ne 0 ]; then
       echo "Error: Pull failed."
       exit 1
   fi

   echo "Pull with rebase successful."
   ```

   2. **Make the Script Executable**

   Open your terminal and run the following command to make the script executable:

   ```bash
   chmod +x ~/scripts/gpull
   (Optional) Add to PATH
   ```

   If you want to run the gpull script from any directory without specifying the full path, you can add ~/scripts to your PATH environment variable.

   3. **Add the following line to your shell configuration file (e.g., .bashrc, .zshrc):**

   ```bash
   export PATH="$HOME/scripts:$PATH"
   ```

   4. Reload your shell configuration with:

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

### Unable to Determine Branch Name

If you see the error message Error: Unable to determine branch name., ensure you are in a Git repository and that your current branch is properly checked out.

### Pull Failed

If the script outputs Error: Pull failed., check your network connection and ensure you have the correct permissions to access the remote repository.

License
This script is provided as-is, without warranty of any kind. Feel free to use and modify it as needed.
