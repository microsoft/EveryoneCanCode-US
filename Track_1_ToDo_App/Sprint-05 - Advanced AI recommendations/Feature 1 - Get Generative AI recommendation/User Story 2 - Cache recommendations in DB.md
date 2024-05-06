# User Story: Cache Recommendations in the Database - Step-by-Step
⏲️ _Est. time to complete: 15 min._ ⏲️

## User Story
*As a user, I want to be able to quickly go back and see the recommendations that were last presented for a given to-do item*

## 🎯Acceptance Criteria:
- The web app should store the recommendations in the database when they are generated.
- The recommendations should be displayed when the user clicks on the recommendations button for the task again.

## 🎓Know Before You Start
no resources at this time

## 📋Steps

In order to complete this user story you will need to complete the following tasks:

### Open Visual Studio Code
Open Visual Studio Code and open the source code the folder with your completed solution from the previous user story if you prefer you can use the starting reference application from [here](/Track_1_ToDo_App/Sprint-05%20-%20Advanced%20AI%20recommendations/src/app-s05-f01-us01/) 

> [!NOTE]
> If you are using Codespaces, the root of your project folder may be in the `/Track_1_ToDo_App/myApplication/` folder
<br/>

### Update the database to store the recommendations in the database

#### 1. Update the database model to store recommendations
The first thing we will need to do is add the recommendations to the database.  Open the `database.py` file and add the following code right under the `recommendations = []` instance variable to create the additional column

```python
recommendations_json = db.Column(db.JSON)    
```

This code adds a new column to the `Todo` model called `recommendations_json` that will store the AI recommendations in JSON format.  **Note we will still keep the `recommendations` instance variable so that it is easy for the UI to work with the collection**.

<br/>

### Update the Application Backend  

#### 1. Update the `app.py` to handle saving and retrieving recommendations
We now need to update the `app.py` to handle saving and retrieving recommendations.  We need to make two changes to this file. (A) import the json module and (B) Replace the recommend route in the `app.py` file with the following code:

A. At the top of the file add the following import statement:

```python
import json
```
B. We will then need to replace the `recommend` route with the following code:

```python
# Show AI recommendations
@app.route('/recommend/<int:id>', methods=['GET'])
async def recommend(id):
    recommendation_engine = RecommendationEngine()
    g.todo = db.session.query(Todo).filter_by(id=id).first()

    if g.todo:
        try:
            #attempt to load any saved recommendation from the DB
            if g.todo.recommendations_json is not None:
                g.todo.recommendations = json.loads(g.todo.recommendations_json)
                return render_template('index.html')
        except ValueError as e:
            print("Error:", e)

    g.todo.recommendations = await recommendation_engine.get_recommendations(g.todo.name)
        
    # Save the recommendations to the database
    try:
        g.todo.recommendations_json = json.dumps(g.todo.recommendations)
        db.session.add(g.todo)
        db.session.commit()
    except Exception as e:
        print(f"Error adding and committing todo: {e}")
        return

    return render_template('index.html')
```

This code updates the `/recommend/<int:id>` route to check if the task has saved recommendations in the database. If the recommendations are found, they are loaded from the database and displayed. If the recommendations are not found, the AI recommendations are generated and saved to the database.

#### 2. Delete the `todos.db` file
Before we can test this change, we will need to delete the `todos.db` file in your directory which will cause all the data in the database to be lost. This is needed because the database schema has changed due to the new column being added to the database table and SQL cannot just add a column without some additional work to migrate data. This approach works fine when you are in development, but if this was a production system you would want to update the database schema and migrate the data when introducing changes. 

> [!WARNING]
> If you do not delete the `todos.db` file you will get an error when you run the app.  The error will be something like `sqlalchemy.exc.OperationalError: (sqlite3.OperationalError) no such column: todos.recommendations_json`.  This error is because the database schema does not match the model.

<br/>

#### 3. Run the Application
Now let's see this functionality in action.  Open the terminal and navigate to the folder where your `app.py` file is located. Run the application by typing `python app.py` and pressing the enter key or simply click the play button in the top right corner of the Visual Studio Code window.  For Codespaces, the easiest path is to just click the play button.   This will launch a browser and show the home page (or you can browse to http://localhost:5000).

    
<br/>
🎉 Congratulations! You have now saved the AI recommendations to the database. This will allow users to quickly go back and see the recommendations that were last presented for a given to-do item.

<br/>

> [!NOTE]
> 📄For the full source code for this exercise please see [here](/Track_1_ToDo_App/Sprint-05%20-%20Advanced%20AI%20recommendations/src/app-s05-f01-us02/).


<br/>

[🔼 **Home** ](/Track_1_ToDo_App/README.md) | [**◀ Previous user story**](User%20Story%201%20-%20Get%20Gen%20AI%20recommendation.md) | [**Next user story** ▶](User%20Story%203%20-%20Refresh%20Recommendations.md)
