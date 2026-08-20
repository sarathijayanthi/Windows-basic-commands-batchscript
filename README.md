# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
```
mkdir sarathi
```
## COMMAND AND OUTPUT
<img width="2172" height="724" alt="image" src="https://github.com/user-attachments/assets/4fc42c49-aecf-4fa8-a6e8-d24897539bb5" />


Remove the directory "my-folder"
```
rmdir sarathi
```
## COMMAND AND OUTPUT

<img width="907" height="128" alt="BCO 573d61a8-d910-42be-a87a-447f362818c2" src="https://github.com/user-attachments/assets/085e8327-a292-42af-a6f2-30e7e19b0789" />


Create the file Rose.txt
```
type nul > rose.txt
```
## COMMAND AND OUTPUT
<img width="948" height="56" alt="image" src="https://github.com/user-attachments/assets/83368c62-8a46-4b49-bde8-8dffa9cc69a5" />


Create the file hello.txt using echo and redirection
```
echo Hello world > hello.txt
```
## COMMAND AND OUTPUT
<img width="950" height="51" alt="image" src="https://github.com/user-attachments/assets/f05a4573-f598-4975-911c-8f0a72cbf66e" />

Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
## COMMAND AND OUTPUT
<img width="1015" height="66" alt="image" src="https://github.com/user-attachments/assets/b49598bd-ed98-4f48-bbe8-9eb2a173305f" />

Remove the file hello1.txt
```
del hello1.txt
```
## COMMAND AND OUTPUT
<img width="1167" height="57" alt="image" src="https://github.com/user-attachments/assets/0e37bd2d-4805-4387-95e9-14868ef586ec" />

List out the file hello1.txt in the current directory
```
dir hello1.txt
```
## COMMAND AND OUTPUT
<img width="1161" height="185" alt="image" src="https://github.com/user-attachments/assets/2aabe0fa-ffca-40f5-a67d-a455beeaeb1c" />

List out all the associated file extensions 
```
assoc
```
## COMMAND AND OUTPUT
<img width="1020" height="544" alt="Screenshot 2026-08-19 133905" src="https://github.com/user-attachments/assets/5b932f15-57f4-4501-b6a1-c5c13648c3b5" />


Compare the file hello.txt and rose.txt
```
fc hello.txt rose.txt
```
## COMMAND AND OUTPUT
<img width="756" height="160" alt="image" src="https://github.com/user-attachments/assets/2aae8a83-f694-43cb-9714-adf600b6ed98" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%
pause
```




## OUTPUT
<img width="427" height="76" alt="image" src="https://github.com/user-attachments/assets/e3f3bcf9-364e-44ad-a068-55425b737b54" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```
## OUTPUT
<img width="1897" height="182" alt="image" src="https://github.com/user-attachments/assets/b5335068-1289-4e9c-a669-3980464f4bc6" />




Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```



## OUTPUT

<img width="1874" height="149" alt="image" src="https://github.com/user-attachments/assets/1c76da61-de69-4469-8bfb-fd9fc695f4bd" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT
<img width="1702" height="60" alt="image" src="https://github.com/user-attachments/assets/d46eb571-27e8-49d5-8ad4-807b4fd91592" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT 1
<img width="1919" height="212" alt="image" src="https://github.com/user-attachments/assets/c079f694-8582-4d2b-9b0c-0c2cb9ca47ea" />

## OUTPUT 2
<img width="1919" height="231" alt="image" src="https://github.com/user-attachments/assets/3f277c7d-9321-43a4-97af-965ddc456a4e" />

## OUTPUT 3
<img width="1919" height="213" alt="image" src="https://github.com/user-attachments/assets/a5b17e6e-f64f-4970-a204-4774510d4edd" />



# RESULT:
The commands/batch files are executed successfully.

