EasyFileOpener is a lightweight command-line utility to manage and execute custom commands easily. You can store commands in a binary file, read them, search, delete, and execute them through a simple CLI interface.

Features

Add new commands with optional templates.

Read and list all saved commands with descriptions.

Execute saved commands directly from the terminal.

Search for commands by name.

Delete commands or purge the entire database.

Automatic file structure update for new versions.

CLI-friendly output with visual success (✔) and failure (✖) indicators.

Installation

Clone the repository:

git clone https://github.com/study-love-edm/easyfileopener.git
cd easyfileopener


Compile the project using make:

make


This will generate the executable easyopen.

Usage
./easyopen [option] command_name


Options:

Option	Description
-r	Read and list a command by name
-w	Write a new command (./easyopen -w command_name)
-e	Execute an existing command (./easyopen -e command_name)
-h	Display help menu
-p	Purge all commands from the database
-s	Search for a command by name
-d	Delete a command by name

Example:

# Add a new command
./easyopen -w mycommand

# Execute a command
./easyopen -e mycommand

# List a command
./easyopen -r mycommand

# Delete a command
./easyopen -d mycommand

Command Templates

You can use templates for predefined commands.

Currently supported templates:

Template	Description
--google	Opens a URL in Google Chrome using a specific profile.

Example:

./easyopen -w --google mywebsite


The program will prompt for the website link to open with Chrome.

How It Works

Commands are stored in a binary file .command.bin.

Each entry includes:

Command name

Executable command

Description

Active status

Deleted commands are marked inactive and can be flushed from the file.

File structure updates automatically if command structure changes.

Code Structure
study-love-edm-easyfileopener/
├── EasyFileOpener.cpp   # Main program & CLI interface
├── Fileop.cpp           # Command operations (read/write/execute/search/delete)
├── Fileop.hpp           # Function declarations for Fileop.cpp
├── helper.cpp           # Helper functions (sorting, file cache, templates)
├── helper.hpp           # Helper declarations and Command structs
└── .command.bin         # Binary file storing commands (auto-generated)

Dependencies

Standard C++ library

C++11 or higher (for compilation)

Compile
g++ -std=c++11 -Wall *.cpp -o easyopen

Notes

Visual indicators in CLI:

✔ (active command)

✖ (inactive or deleted command)

The binary file .command.bin is automatically created on first run.

File updates and cache cleaning happen automatically in the background.

any problem for build : do mail : ssasmal287@gmail.com


License

(C) 2025 Souvik Sasmal. All rights reserved.
