# Environment-Variables---Task-7

project:
  name: "Environment Variables & PATH"
  platform: "Linux (Ubuntu)"
  shell: "bash"
  level: "Beginner to Intermediate"

objective:
  - Understand environment variables
  - Work with PATH variable
  - Create temporary and persistent variables
  - Debug PATH-related issues
  - Fix missing command issues correctly

tools:
  primary:
    - Linux Terminal
    - bash shell
  package_manager:
    - apt

concepts:
  environment_variable:
    description: "Key-value pair used by the shell and programs to control behavior"
    examples:
      - HOME
      - USER
      - PATH

  PATH:
    description: "Colon-separated list of directories searched for executables"
    example: "/usr/bin:/bin:/usr/local/bin"

tasks_performed:
  - View environment variables
  - Create custom variables
  - Modify PATH variable
  - Make variables persistent
  - Test changes
  - Debug PATH issues
  - Document configuration

commands:
  view_all_variables:
    - command: "printenv"
      explanation: "Displays all environment variables in the current shell"

  view_single_variable:
    - command: "echo $PATH"
      explanation: "Prints the value of PATH variable"

  create_variable_temporary:
    - command: "export MYVAR=hello"
      explanation: "Creates a temporary environment variable for current session"

  add_directory_to_path:
    - command: "export PATH=$PATH:/home/user/scripts"
      explanation: "Appends a new directory to PATH without overwriting existing entries"

  make_persistent:
    - command: "nano ~/.bashrc"
      explanation: "Opens bash configuration file for persistent variables"

    - command: "source ~/.bashrc"
      explanation: "Reloads bash configuration without restarting terminal"

  check_command_path:
    - command: "which python3"
      explanation: "Shows the exact path of the executable used by shell"

  debug_path:
    - command: "echo $PATH | tr ':' '\n'"
      explanation: "Displays PATH directories line by line for debugging"

issue_faced:
  description: "python command not found and incorrect manual directory creation"
  symptoms:
    - "/usr/bin/python: No such file or directory"
    - "type: python: not found"
    - "mkdir /usr/bin/python attempted"

root_cause:
  - Python was not installed
  - Misunderstanding that PATH creates executables
  - Incorrect use of mkdir to create system binaries

incorrect_approach:
  - command: "mkdir /usr/bin/python"
  - reason: "Executables are files installed via package manager, not directories"

correct_fix:
  install_python:
    - command: "apt update"
    - command: "apt install -y python3"
    - explanation: "Installs python3 binary properly into /usr/bin"

  verify_installation:
    - command: "python3 --version"
    - command: "which python3"

  optional_alias:
    - file: "~/.bashrc"
    - entry: "alias python=python3"
    - explanation: "Allows using 'python' command for python3"

best_practices:
  - Never overwrite PATH completely
  - Always append or prepend using $PATH
  - Do not manually create files in /usr/bin
  - Use package manager to install missing commands
  - Verify executable location using which or type

final_outcome:
  - Environment variables understood
  - PATH managed safely
  - Python installed correctly
  - Common beginner mistakes avoided
  - System remains stable
