# 📖 User Story: Remove Item through Web Form - User Story: Step-by-Step
⏲️ _Est. time to complete: 15 min._ ⏲️

## User Story

*As a user, I want to be able to remove items from my to-do list*

## 🎯Acceptance Criteria:
- The web app should provide a form for users to input data.  
- The web form should capture the task number of the item the user would like to remove.
- The application should remove the task from the list when the form is submitted.
- The interface should look something like this:

    ![outcome1](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/outcome-S02-f01-US03.png)

## 🎓Know Before You Start
no resources at this time

## 📋Steps

In order to complete this user story, you will need to complete the following tasks:

### Open Visual Studio Code
Open Visual Studio Code (either locally in the project directory you setup or through your Codespace). Visual Studio Code should have your completed solution from the end of Sprint-01 or if you prefer you can use the starting reference application from [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f01-us02/) by copying it over into your local directory or Codespace.

### Updating the Web Application Frontend
We need to update the web application's user interface to allow the user to remove items via the web page.

#### 1. Update the user interface
Update the `index.html` to add a basic form to allow a user to remove tasks. This form will call the backend server functionality when the user hits the 'Remove' button. Your HTML should be updated to look like this:

```html
<!DOCTYPE html>
<html>
<head>
    <title>To-Do List</title>
</head>
<body>
    <h1>To-Do List</h1>
    <ol>
        {% for todo in todo_list %}
            <li>{{ todo }}</li>
        {% endfor %}
    </ol>
    <form action="/add" method="post">
        <label for="todo">Add a to-do:</label>
        <input type="text" name="todo">
        <button type="submit">Add</button>
    </form>
    <form action="/remove" method="post">
        <label for="item_number">Remove task number:</label>
        <input type="number" name="item_number" min="1">
        <button type="submit">Remove</button>
    </form>
</body>
</html>
```

The code above creates a second form to allow users to input a task number representing the to-do item they would like to remove. When the form is submitted, a POST request is sent to the `/remove` URL, which triggers the remove_todo function in the Python code.

### Updating the Web Application Backend
Similar to the steps in the last sprint to enable the server to handle new to-do items, we need to update the Python code to enable the backend server to handle the removal of to-do items via the `/remove` URL.

#### 1. Add a Remove Route
Add a remove route to enable a user to remove tasks. Add the following code just below the add route code:

>[!TIP]
>You can use GitHub Copilot to add this function with a prompt such as *add a route to remove item based on item number*
        
```python
@app.route("/remove", methods=["POST"])
def remove_todo():
    item_number = int(request.form["item_number"])
    if 0 < item_number <= len(todo_list):
        todo_list.pop(item_number - 1)
        save_todo_list()
    return redirect(url_for("index"))
```

The code above creates a new route listening for POST requests from the `/remove` URL. When a POST request is received, the function remove_todo is called. This function retrieves the value of the "item_number" form field from the request, converts it to an integer, and then removes the task at the specified index from the todo_list. Note again, Python collections are zero-based while our displayed list is one-based, so we need to subtract 1 from the item_number to get the correct index. The save_todo_list function is then called to save the updated list to the file, and the user is redirected back to the index page.

<br/>

#### 2. Run the Application
Open the terminal and navigate to the folder where your `app.py` file is located. Run the application by typing `python app.py` and pressing the enter key or click the play button in the top right corner of the Visual Studio Code window. For Codespaces, just click the play button. This will launch a browser and show the home page (or you can browse to http://localhost:5000). 

Test it out by adding a task and then removing a task.

Your application should look something like this:

![outcome3](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/outcome-S02-f01-US03.png)

<br/>

Stop the server by pressing `CTRL-C` in the terminal window where the web server is running.

<br/>

🎉 Congratulations! You have now updated your basic web application to include a form to allow both adding AND removing tasks.

<br/>

> [!NOTE]
> 📄For the full source code for this exercise, please see [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f01-us03/).

[🔼 Home ](/Track_1_ToDo_App/README.md) | [**◀ Previous user story**](User%20Story%202%20-%20Add%20Item%20through%20Web%20Form.md) | [**Next user story** ▶](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%202%20-%20Basic%20Styling/User%20Story%201%20-%20Add%20Basic%20Styling%20to%20the%20Web%20App.md)
