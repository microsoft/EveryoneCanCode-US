# 📖 Load To-Do items from a file - Step-by-Step
⏲️ _Est. time to complete: 15 min._ ⏲️

## User Story

*As a user, I want to be able to have my to-do list automatically loaded from a file when I start the program.*

## 🎯Acceptance Criteria:
- Existing to-do list items from the last time I ran the program are loaded into this program
- The existing to-do list items will be a ".txt" file
- each line in the file will contain a single to-do item.
- if there is no file, then the program should load an empty collection

## 🎓Know Before You Start
The following resources/videos will help you get a better understanding of some of the basic Python concepts that you will use to complete this user story.
- [Working with Files](https://youtu.be/uQ5BZht9L3A?t=5812) (~ 1 min) - Same video as from previous user story <br/>
- [Exception Handling](https://www.youtube.com/watch?v=HQqqNBZosn8&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=17) (12:53 min) <br/>
- [Exception Handling Demo](https://www.youtube.com/watch?v=LrRh-V-hYEc&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=18) (3:57 min) <br/>
    

## 📋Steps

In order to complete this user story you will need to complete the following tasks:

### Start your Codespace or Open Visual Studio Code locally
<details>
<summary>click <b>here</b> if you are running in Codespaces</summary>

If you are using a Codespaces, please go into the repo that you created for this project and start the codespace by directly clicking on the Codespace name.  In the case of the image below, the Codespace is named _symmetrical computing-machine_. Note however, that each Codespace auto-generates a unique name for that code space so your Codespace name will be different.  

![Start Codespaces](/Track_1_ToDo_App/content-images/github-start-codespace.png)

This will take you directly into a online visual studio code environment.

![online visual studio code](/Track_1_ToDo_App/content-images/github-start-codespace-02.png)
</details>

<details>
<summary>click <b>here</b> if you are running Visual Studio Code in a local development environment</summary>

- From the terminal/console window, navigate to the project directory
  
    ```bash
    cd <project directory>
    ```
- Open up Visual Studio Code in the project directory by executing the following command.
    
    ```cmd
    code . 
    ```
</details> 

<br/>

Open the `app.py` file in the root of your project folder.

<br/>

### Updating the code base for new functionality

#### 1. Update code to load to-do list from file on start
The first change that we will need to make to the code is to update the logic for the start of the program. We will need to add code that will load the to-do list from a file when the program starts.  Add the following code to the beginning of the program, right after the `todo_list = []` statement:

![insertcode](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/images/InsertCode-S1-F2-US02-01.png)

>[!TIP]
>You can ask GitHub Copilot to help here with this prompt *load todo list from todo_list.txt file*

```python
try:
    with open("todo_list.txt", "r") as file:
        for line in file:
            todo_list.append(line.strip())
except FileNotFoundError:
    print("No saved items found")
    pass
```

This code will open a file named `todo_list.txt` in the current directory and read each line from the file.  The `r` parameter in the `open` function tells Python to open the file in read mode.  The `for` loop will iterate through each line in the file and add it to the `todo_list`.  The `strip` function is used to remove any leading or trailing whitespace from the line before adding it to the `todo_list`.  If the file does not exist, the `except FileNotFoundError` block will catch the error and the program will first print a message letting the user know that it didn't find any previously saved items and then continue without loading any items. As an example, if you are running the program for the very first time, that file would not have been created so the exception would get thrown and in this case we want the program to continue to execute.

<br/>

#### 2. Run the application
Now let's see this application in action. Open the terminal and navigate to the folder where your `app.py` file is located. Run the application by typing `python app.py` and pressing the enter key or simply click the play button in the top right corner of the Visual Studio Code window.

- When you start the program you should automatically see the list of to-do items that were previously saved in the file.

<br/>

 > [!NOTE]
 > 📄For the full source code for this exercise please see [here](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/src/app-s01-f02-us02/app.py)


<br/>

[🔼 Home ](/Track_1_ToDo_App/README.md) | [**◀ Previous user story**](User%20Story%201%20-%20Save%20To-Do%20List%20to%20File.md) | [**Next user story** (in next sprint) ▶](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%201%20-%20Web%20App%20Conversion/User%20Story%201%20-%20Convert%20To%20Web%20App.md)