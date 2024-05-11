# 📖 User Story: Add Item through Web Form - Step-by-Step
⏲️ _Est. time to complete: 15 min._ ⏲️

## User Story

*As a user, I want to input tasks through a web form, so I can interact with the application easily.*

## 🎯Acceptance Criteria:
- The web app should provide a form for users to input data.
- The form should simply capture the name of the to-do item, similar to the original terminal app for a seamless transition.
- The application should add the task to the list when the form is submitted.
- The interface should look something like this:

    ![outcome1](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/outcome-S02-f01-US02.png)

## 🎓Know Before You Start
no resources at this time

## 📋Steps

In order to complete this user story, you will need to complete the following tasks:

### Updating the Web Application Frontend
The first change is to update the web application's user interface to allow the user to add new items via the web page.

#### 1. Open Visual Studio Code
Open Visual Studio Code (either locally in the project directory you setup or through your Codespace). Visual Studio Code should have your complete solution from the end of Sprint-01 - or if you prefer you can use the starting reference application from [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f01-us01/) by copying it over into your local directory or Codespace.

#### 2. Update the User interface to Add New To-Do Items
We need to update the `index.html` to include a basic form to allow a user to add tasks and then subsequently call the backend server to add it to the file. Your HTML should be updated to look like this:

>[!TIP]
>You can use GitHub Copilot with a prompt like *add form to add task with add route*

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
</body>
</html>
```
The code above creates a simple form allowing users to enter the name of a to-do item. When the form is submitted, a POST request is sent to the `/add` URL which will trigger functionality in the back-end to save the to-do item to a file. A POST request sends all of the data in the form to the back-end server.

<br/>

### Update the Web Application Backend
The next set of changes we will need to make is to update the Python code to enable the backend server to handle our `/add` functionality for adding a new to-do item to the collection.

#### 1. Update Web Server to Handle New To-Do Items
We need to update the Python code to enable the backend server to handle new to-do items. This will be accomplished by adding a new route to support this functionality. To do this, open up the `app.py` file and add the following right after the homepage route/index function:

```python
@app.route("/add", methods=["POST"])
def add_todo():
    todo = request.form["todo"]
    todo_list.append(todo)
    save_todo_list()
    return redirect(url_for("index"))
```

The code above creates a new route listening for POST requests to the `/add` URL. When a POST request is received, the function add_todo is called. This function retrieves the value of the "todo" form field from the request, appends it to the todo_list, saves it to the file and then redirects the user back to the index page.

Because the `save_todo_list()` function is not yet implemented so you may see a squiggly, yellow line underneath the function call.  

![save_to_do_list error](../images/save_to_do_list%20error.png)

Don't worry. We will add it in the next step.

<br/>

#### 2. Add Function to Save To-Do List
To complete the back-end web server functionality, we need the ability to save these tasks to our file so they persist between sessions (similar to the save functionlity we had in Sprint-01). Implement a function to write tasks to the file. Please add the code below right after the `add_todo()` function:

>[!TIP]
>You can use GitHub Copilot to create this with a prompt such as *Add a route to save todo list items*

```python
def save_todo_list():
    with open(todo_file, "w") as file:
        for todo in todo_list:
            file.write(todo + "\n")
```

You should notice the swiggly, yellow line in the previous step should have disappeared as this function has now been defined.

<br/>

#### 3. Run the Application
Open the terminal and navigate to the folder where your `app.py` file is located. Run the application by typing `python app.py` and pressing the `<ENTER>` key or simply click the play button in the top right corner of the Visual Studio Code window. For Codespaces, just click the play button. This will launch a browser and show the home page (or you can browse to http://localhost:5000).

Test it out by adding a tasks.
    
![RunApp-S2-F1-US02-01](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/outcome-S02-f01-US02.png)

<br/>

> [!NOTE]
>To stop the server simply hit `CTRL-C` in the terminal window where the web server is running.

<br/>

<br/>
🎉 Congratulations! You have now updated your basic web application to include a form that allows a user to add tasks and persist them a file.

<br/>

> [!NOTE]
> 📄For the full source code for this exercise please see [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f01-us02/).

<br/>

[🔼 Home ](/Track_1_ToDo_App/README.md) | [**◀ Previous user story**](User%20Story%201%20-%20Convert%20To%20Web%20App.md) | [**Next user story** ▶](User%20Story%203%20-%20Remove%20Item%20through%20Web%20Form.md)




