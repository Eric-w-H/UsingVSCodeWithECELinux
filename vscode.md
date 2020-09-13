# VSCode Setup for ECE 2400

### Important Notes:

- This is **ENTIRELY OPTIONAL!**
  - You can excel in this course with the default setup, using X2Go and Geany or Micro (or any of the other editors, for that matter).
  - VSCode is merely an alternative with some advantages and disadvantages, the most apparent of which is that VSCode does *not* support remote desktop, screenshare, or GUI access.
  - Following this tutorial does not break your X2Go setup!

- It is **HIGHLY** recommended that you install [git](https://git-scm.com/downloads) (https://git-scm.com/downloads) on your local machine before downloading VSCode.
  - You can check for a git install by running `git --version` from the command line.
  - Having git pre-installed allows VSCode to automatically integrate with the toolchain, which will make your life easier in the future.

- If you need help with anything in this document, just like with any of the other tutorials, reach out. The course staff are here to help you!

- Don't open Micro (or any other editor) in VSCode's terminal! By default, VSCode will consume keyboard shortcuts before they reach the terminal, so `ctrl-q` to close Micro *won't reach Micro!* Use `code /directory/or/filename` instead of `micro /path/to/filename`.


## Introduction to VSCode
VSCode is a free, lightweight text editor with a thriving ecosystem of extensions and plugins, allowing it to function as a full-featured IDE for languages from C to Javascript. You can download it from [here](https://code.visualstudio.com) (https://code.visualstudio.com), which also hosts a wonderful [Getting Started](https://code.visualstudio.com/docs) page.

- Extensions are installed from the aptly-named "Extensions" tab on the left sidebar, accessible by clicking the 'four blocks' symbol in the leftmost column, the keyboard shortcut `Ctrl-Shift-X` on Windows/Linux and `Cmd+Shift+X`, from View->Extensions, or by typing "install extensions" and selecting "Extensions: Install Extensions" from the command palette.

- The **Command Palette** is VSCode's window to *everything*. It functions as a search window and interactive prompt for some commands, and is incredibly convenient. You can access it using `Ctrl+Shift+P` on Windows/Linux and `Cmd-Shift-P` on Mac.

### Extensions
Remember that extensions sidebar? You will need two at a bare minimum, though there are many, many others that you might find useful, and they can be disabled or uninstalled at any time if you decide you don't like what they do. If your version numbers differ from the ones in the screenshot, don't worry. Most extensions update fairly frequently.
- The two required extensions:
  - C/C++ (by Microsoft)
  - Remote -- SSH (by Microsoft)

![Remote-SSH Extension](resources/remote-ssh-extension.png) ![C/C++ Extension](resources/c-cpp-extension.png)

- Some other handy extensions:
  - Git History (by Don Jayamanne),
  - GitLens – Git Supercharged (by Eric Amodio)
  - C/C++ IntelliSense (by austin)
  - Visual Studio IntelliCode (by Microsoft)
  - Python (by Microsoft)
  - Remote – SSH: Editing Configuration Files (by Microsoft)
  - ... and many, many more.

## Remote Development with VSCode

1. Use `Ctrl-Shift-P` on Windows/Linux, or `Cmd-Shift-P` on Mac, to open the Command Palette.

2. Start typing "connect current window to host" and select `Remote-SSH: Connect Current Window to Host...`

![Accessing Remote-SSH via Command Palette](resources/remote-ssh-cmd-palette.png)

3. Select "Add New SSH Host" and type in the ssh command: `ssh <netID>@ecelinux.ece.cornell.edu`, replacing `<netID>` with your netID.

    1. If VS Code prompts you to select a configuration file, select the configuration file in your home folder. This may look like `/Users/<username>/.ssh/config` on Mac/Linux, or `C:\Users\<username>\.ssh\config` on Windows.

    2. If VS Code shows you a prompt saying "Host added!" with a "Connect" button, hit the "Connect" button.

4. VSCode should prompt you for your password to the server, go ahead and provide it.
   - VSCode should now open into a blank window and do some setup on the server. Be patient, the first time can take a minute to complete.
   - If you get a warning about git version, remember to run `source setup-ece2400.sh --enable-auto-setup`.
5. Navigate your instance using the integrated terminal (access with the keyboard shortcut ```ctrl + ` ```).
   - You can open a folder in VSCode with `code .`, or individual files with `code <filename>`.
   - You can debug your compiled programs with perf & gdb, and use any of the other command-line programs.
  
![Using the terminal](resources/remote-whoami.png)

6. You'll need to install any extensions you want to use again on the server. Simply open the extensions tab with `Ctrl-Shift-X` on Windows/Linux and `Cmd+Shift+X` on Mac. Search up the extensions, and click "install on server". You only need to do this once, VSCode will remember what's installed.

7. To close a remote connection, you can exit VS Code on your local machine, or you can open the command pallette and type "close remote connection", then select "Remote: Close Remote Connection".

### References and Resources
https://code.visualstudio.com/docs/remote/ssh 
- Includes instructions on how to use ssh profiles to login with keys instead of using your password each time.

https://code.visualstudio.com/docs/getstarted/keybindings
- Details on VSCode's keybindings.