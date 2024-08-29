# Handhold Command-Line Tool

## Overview

**Handhold** is a command-line tool designed to help you manage and execute sequences of commands stored in instruction set files. These instruction sets are stored in the `~/.handhold/` directory and are easily accessible via the `handhold` command. With Handhold, you can load a set of instructions and step through each command one at a time using a simple key binding.

## Features

- Load and execute command sequences from `.instruct` files.
- Cycle through commands with a single key press (`Ctrl+k` by default).
- Easily review and execute commands directly from the command line.

## Installation

### Prerequisites

- **Bash**: Handhold works with both `bash` shell only.

### Step 1: Download the Script

1. Download the `handhold` script and place it in a directory in your `$PATH`. You can use the following command to download it directly:

    ```bash
    curl -o /usr/local/bin/handhold https://raw.githubusercontent.com/rtaylorzfin/handhold/main/handhold
    chmod +x /usr/local/bin/handhold
    ```

### Step 2: Create the `~/.handhold/` Directory

2. Create the `~/.handhold/` directory where your instruction set files will be stored:

    ```bash
    mkdir -p ~/.handhold/
    ```

### Step 3: Add Key Bindings to Your Shell Configuration

3. Add the following code to your shell configuration file (e.g., `~/.bashrc` ):

    ```bash
    source /usr/local/bin/handhold
    ```

    - **Ctrl+k** is the default key binding to cycle through commands. You can change it by modifying `\C-k` to another key combination in /usr/local/bin/handhold.

### Step 4: Source Your Shell Configuration

4. After adding the above code, reload your shell configuration:

    ```bash
    source ~/.bashrc
    ```

## Usage

### Loading an Instruction Set

1. To load an instruction set, use the following command:

    ```bash
    handhold load mytask
    ```

   This command looks for a `mytask.instruct` file in the `~/.handhold/` directory and sets it as the active instruction set.

### Cycling Through Commands

2. Once an instruction set is loaded, press `Ctrl+k` to load the first command from the instruction set into your command line. Press `Enter` to execute the command.
3. Press `Ctrl+k` again to load the next command in the sequence, and so on.

### Example

- Create a file `~/.handhold/mytask.instruct` with the following content:

    ```bash
    echo "Hello, World!"
    ls -la
    pwd
    ```

- Run `handhold load mytask` to set `mytask.instruct` as the active instruction set.
- Press `Ctrl+k` to cycle through and execute the commands one by one.

## Uninstallation

1. Remove the `handhold` script from your `$PATH`:

    ```bash
    rm /usr/local/bin/handhold
    ```

2. Remove the key bindings from your shell configuration by deleting the lines you added in Step 3.

3. Optionally, remove the `~/.handhold/` directory if you no longer need it:

    ```bash
    rm -rf ~/.handhold/
    ```

## License

Handhold is released under the MIT License.
