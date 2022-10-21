# Setting Up Windows Computer for Python Development

1. Install Windows Terminal
    - Set LocalMachine execution policy: Open a PowerShell prompt as Administrator, run **Set-ExecutionPolicy -ExecutionPolicy Unrestricted**


2. Install Miniforge
    - Accept all defaults. 


3. Open Windows Terminal. In PowerShell, follow [these]( https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Windows-x86_64.exe) instructions to run **conda init** and set **auto_activate_base** to false. 
    - Then run **conda init -all**, so you can use conda from Git Bash later on. 

4. Install VSCode and the following extensions: Python, Remote - SSH

4. Install Git for Windows. Accept all defaults, except:
    - Make sure to select the option that adds a git-bash profile to Windows Terminal. 
    - Make sure to select Visual Studio Code as your default editor for resolving merge conflicts. 
    - Enable support for pseudo-consoles. 

5. Optional: To use Git Bash as your default shell:
    - Open Windows Terminal. Go to Settings. Set Default Profile to Git Bash. Restart Windows Terminal. 

6. Optional: Install Mamba: **conda install mamba -n base -c conda-forge** 
    - Configure your shells to be aware of mamba: conda activate base; mamba init -all
    - You can now choose to use mamba as a drop-in replacement for the conda command pretty much anywhere, often with significantly improved performance. 

- mamba init by default added a path to my bash profile that it could not recognize. It used a cygwin path (/cygdrive/c/...etc.) that wasn't working even after installing cygwin. I just changed it to C:\ and it worked fine.