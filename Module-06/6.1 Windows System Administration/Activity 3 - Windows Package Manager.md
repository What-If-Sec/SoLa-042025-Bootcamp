## Activity Objective
Students will successfully download and install the Chocolatey Windows package manager, and use it to install at least three commonly used desktop applications (e.g., Google Chrome, Spotify, Skype) via the command line, demonstrating basic proficiency with package management in a Windows environment.

## Activity Instructions
Follow the instructions below to install choco as well as Google Chrome, Spotify, and Skype.
1. Open the Windows CMD with admin privileges.
2. Copy and paste the command below to download and install choco.
````cmd
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
````
3. Wait a few seconds for the command to complete.
4. If you don’t see any errors, you are ready to use Chocolatey CLI!
5. Type `choco -?` to view the Getting Started usage instructions.
6. Install Google Chrome to your Windows VM by running `choco install google-chrome-x64`
7. Verify that Google Chrome has been installed on your VM by executing `start chrome` in the CMD prompt.
8. Install Skype to your Windows VM by running `choco install skype`.
9. Verify that Skype  has been installed on your VM by executing `start skype` in the CMD prompt.
10. Install Spotify to your Windows VM by running `choco install spotify`.
11. Verify that Spotify  has been installed on your VM by executing `start spotify` in the CMD prompt.
