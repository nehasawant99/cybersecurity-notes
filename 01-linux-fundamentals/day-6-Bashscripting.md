## Bash Scripting Basics

## Objective

Today I learned the fundamentals of Bash scripting on Kali Linux by writing simple scripts to automate common Linux tasks.

## Topics Covered
Creating Bash scripts
- Shebang (#!/bin/bash)
- Comments
- Variables
- User input

## Scripts

### hello.sh
Prints a welcome message.

### variables.sh
Demonstrates how to create and use variables.

### user_input.sh
Reads input from the user using the `read` command.


## Commands Practised

- echo
- read

## Skills Learned

- Writing executable Bash scripts
- Using variables and user input

## Issues Faced
Issue: The project folder was owned by root instead of my user (neha), so I couldn't create, edit, or save files.

- Solution: Changed the folder ownership to my user using:
- Command: sudo chown -R neha:neha ~/Desktop/cyberlab

## Screenshots

- Using the command nano to create hello.sh script and writing the script for variables, printing data and user input
- Save: Ctrl + O > Enter > Ctrl + X

  
<img width="685" height="511" alt="Screenshot 2026-07-01 at 7 05 23 PM" src="https://github.com/user-attachments/assets/cb9494c0-f718-40d9-9112-281e25400062" />


- chmod +x hello.sh. Used this command for script permissions and execution
- To execute the script, the command I have used is ./hello.sh

  
<img width="355" height="161" alt="Screenshot 2026-07-01 at 7 05 06 PM" src="https://github.com/user-attachments/assets/2875f577-df63-438d-be44-7eadcbc3d632" />


