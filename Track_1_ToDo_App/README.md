# Build a To-Do Application with AI Features

## Summary
This training is designed to help students build a To-Do application with AI features that will be deployed to Azure.  The application will start as a simple console/terminal application and then evolve into a web application taking advantage of generative AI to help with task recommendations.  The application will be broken down into a series of sprints that will build on top of each other.  Each sprint will have a set of features and user stories that the students will implement.  The goal is to give students a hands-on experience building a real-world application that they can continue to evolve after the hackathon.

## Key Concepts that Students will Learn:
- **Everyone can code** – and coding can come in all shapes and sizes; from a simple script/console application, to a website, to a fully commercial solution that scales to millions of users.  You do not have to build the next Facebook or YouTube to be a developer.

- **Start Small and iterate** – some problems can be daunting if you try to solve them all at once. Break down a problem into smaller chunks that you can iterate over and incrementally make improvements to your application over time.  We have purposely broken down the problem into a series of sprints and user stories to help show how an application can evolve over many iterations. 

- **Understand the tools that can help you on the journey**:  such as IDE’s (i.e., Visual Studio Code) and how AI can both help you build your application (i.e., GitHub Copilot) as well as help you create applications with amazing capabilities

## Track Structure
- Students will be broken up into teams based on skill level and each team will be assigned a coach (i.e., CSA) to guide them through two days of learning.
- The training will be centered around building a **To-Do Application**.  Taking the students from the most basic console/terminal application, to a web application, **adding AI features** along the way, and then eventually **hosting in Azure**.
- The application will be broken down into a small set of manageable tasks (i.e., sprints and user stories) building up to the final application.  Each sprint will have some learning activities through recorded presentations to get the students up to speed on a topic, and then exercises broken up into features/user stories that they will implement.
- Each sprint will build on top of the previous sprint and students will be very hands on with the code.
    - Since each sprint builds on the previous sprint a student can join at any point in the track and start coding as each user story has a fully functional code base that the user can start from. 
- The students will be able to work at their own pace and will have the ability to ask questions of their coach as they work through the exercises.


## Getting Started
The outline below documents the sprints and user stories that you will be implementing on your journey.  If you want to go through the entire experience, please follow them in order.  However, all user stories have fully functioning code base, so they are designed to pick up from whatever sprint / user story you want to start with.


### Sprint 0 - Environment Setup
⏲️ _Est. time to complete: 45 min._ ⏲️

This sprint is designed to help students get their environment setup and ready to start coding.  The sprint will walk students through setting up their development environment, installing the necessary tools, and getting the code base for the To-Do application.


1. [**Setup a GitHub Account**](/Track_1_ToDo_App/Sprint-00%20-%20Environment%20Setup/01%20-%20Setup%20GitHub%20Account.md)
2. [**Setup the To-Do App Repository**](/Track_1_ToDo_App/Sprint-00%20-%20Environment%20Setup/02%20-%20Setup%20To-Do%20Application%20Repository.md)
3. [**Setup GitHub Code Spaces**](/Track_1_ToDo_App/Sprint-00%20-%20Environment%20Setup/02a%20-%20Use%20GitHub%20CodeSpaces.md)

    <details>
    <summary>click here if you would prefer to setup a local development environment</summary>

    - [**Windows Setup**](/Track_1_ToDo_App/Sprint-00%20-%20Environment%20Setup/02b%20-%20Setup%20Local%20Development%20Environment%20on%20Windows.md) 
    - [**Mac Setup**](/Track_1_ToDo_App/Sprint-00%20-%20Environment%20Setup/02c%20-%20Setup%20Local%20Development%20Environment%20on%20Mac.md)
    </details> 

### Sprint 1 - Basic Application
⏲️ _Est. time to complete: 45-60 min._ ⏲️

This sprint is designed to help students build a basic To-Do application that can be used to store a local to-do list on your computer.  The sprint will walk students through building a simple console application that will allow users to add, delete, and list tasks.  

> [!NOTE]
> **🎓 Know before you start**
> <details>
>    <summary>click here for some videos to help get you started</summary>
>
> - [Development 101](https://www.youtube.com/watch?v=MHS7V-5e0mc)
> - [What is Python?](https://www.youtube.com/watch?v=7XOhibxgBlQ&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=2) (3:10 min)
> - [Python Extention for Visual Studio Code](https://www.youtube.com/watch?v=CXZYvNRIAKM&list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6&index=4) (2:49 min)
> 
> </details>
<br/>

**📕Feature: Manage To-Do List**
1. [**📖 Add Items to List**](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/Feature%201%20-%20Manage%20Todo%20List/User%20Story%201%20-%20Add%20Item%20to%20List.MD)
2. [**📖 Remove Items from List**](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/Feature%201%20-%20Manage%20Todo%20List/User%20Story%202%20-%20Remove%20Item%20from%20List.md) 

**📕Feature: Save To-Do List**
1. [**📖 Save List to File**](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/Feature%202%20-%20Save%20To-Do%20List/User%20Story%201%20-%20Save%20To-Do%20List%20to%20File.md
)
2. [**📖 Load List from File**](/Track_1_ToDo_App/Sprint-01%20-%20Basic%20Application/Feature%202%20-%20Save%20To-Do%20List/User%20Story%202%20-%20Load%20To-Do%20List%20from%20File.md)

<br/>

> [!NOTE]
> This sprint is a reminder that not all code needs to be complex. Not every problem requires a web application or a mobile app. Sometimes a simple script will get the job done!



### Sprint 2 - Web Application
⏲️ _Est. time to complete: 80 min._ ⏲️

This sprint is designed to help students build a web application by evolving the to-do application from sprint 1.  The sprint will walk students through building a simple web application that will allow users to add, delete, and list tasks.

> [!NOTE]
> **🎓 Know before you start**
> <details>
>    <summary>click here for some videos to help get you started</summary>
>   - [Introduction to Web Apps](https://youtu.be/DE3OQyzPeEw)
> </details>
>
<br/>

**📕Feature: Web App Conversion**
1. [**📖 Convert Console App to Web App**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%201%20-%20Web%20App%20Conversion/User%20Story%201%20-%20Convert%20To%20Web%20App.md)
2. [**📖 Add Item through Web Form**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%201%20-%20Web%20App%20Conversion/User%20Story%202%20-%20Add%20Item%20through%20Web%20Form.md)
3. [**📖 Remove Item through Web Form**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%201%20-%20Web%20App%20Conversion/User%20Story%203%20-%20Remove%20Item%20through%20Web%20Form.md) 

**📕Feature: Basic Styling**
1. [**📖 Add Basic Styling to Web App**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%202%20-%20Basic%20Styling/User%20Story%201%20-%20Add%20Basic%20Styling%20to%20the%20Web%20App.md)
2. [**📖 Personalize Website**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/Feature%202%20-%20Basic%20Styling/User%20Story%202%20-%20Personalize%20Website.md) 

### Sprint 3 - Database Integration
⏲️ _Est. time to complete: 25 min._ ⏲️

In this sprint we will be taking the web application from Sprint 2 and adding in the ability to store tasks in a database to persist any changes that are made. This will allow users to access their tasks from any device with internet connectivity and not have to worry about concurrent users competing to write to a local file.

**📕Feature: Shift task storage to database**
1. [**📖 Convert file storage to database storage**](/Track_1_ToDo_App/Sprint-03%20-%20Database%20Integration/Features%201%20-%20Shift%20task%20storage%20to%20database/User%20Story%201%20-%20Move%20from%20File%20Storage%20to%20database.md)


### Sprint 4 - Voice To Text
⏲️ _Est. time to complete: 30 min._ ⏲️

This sprint is designed to help students add voice to text functionality to the To-Do application.  The sprint will walk students through adding voice to text functionality to the To-Do application.

> [!NOTE]
> **💻 Note for Mac M1 Users** - If you are using a Mac M1 device, please note that you will need to use Chrome or Safari as the voice-to-text mechanism used here is not supported in Edge on Mac M1 devices.

**📕Feature: Voice to Text**
1. [**📖 Add ability to use voice to add task name**](/Track_1_ToDo_App/Sprint-04%20-%20Voice%20To%20Text/Feature%201%20-%20Add%20Voice/User%20Story%201%20-%20Add%20Voice.md)


### Sprint 5 - Advanced AI Recommendations
⏲️ _Est. time to complete: 1 hour 10 min._ ⏲️

In this sprint you will be taking the application that you built in Sprint 4 and adding in AI recommendations to help users complete their tasks.  This will be done by leveraging the Azure OpenAI API to generate recommendations based on the task name.

**📕Feature: Advanced AI Recommendations**
1. [**📖 Get Recommendations from Generative AI based on To-Do name**](/Track_1_ToDo_App/Sprint-05%20-%20Advanced%20AI%20recommendations/Feature%201%20-%20Get%20Generative%20AI%20recommendation/User%20Story%201%20-%20Get%20Gen%20AI%20recommendation.md)
2. [**📖 Store the recommendations in the DB for a task**](/Track_1_ToDo_App/Sprint-05%20-%20Advanced%20AI%20recommendations/Feature%201%20-%20Get%20Generative%20AI%20recommendation/User%20Story%202%20-%20Cache%20recommendations%20in%20DB.md)
3. [**📖 Allow the user to refresh the recommendations**](/Track_1_ToDo_App/Sprint-05%20-%20Advanced%20AI%20recommendations/Feature%201%20-%20Get%20Generative%20AI%20recommendation/User%20Story%203%20-%20Refresh%20Recommendations.md)


### Sprint 6 - Add additional details about to-do item
⏲️ _Est. time to complete: 45 min._ ⏲️

This sprint is designed to help students add additional details to the To-Do application.  The sprint will walk students through adding details about the task such as Due Date, Priority, additional Notes, and whether or not the to-do item has been completed.

**📕Feature: Add additional about to-do item**
1. [**📖 Add Due Date, Priority, Notes and Completion Status to To-Do item**](/Track_1_ToDo_App/Sprint-06%20-%20Advanced%20To-Do%20Details/Feature%201%20-%20Add%20Additional%20To-Do%20Details/User%20Story%201%20-%20Add%20additional%20details%20to%20to-do%20item.md)


### Sprint 7 - Advanced Styling in your Web Application
⏲️ _Est. time to complete: 1 hour 35 min._ ⏲️

This sprint is designed to help students add advanced styling to the To-Do application.  The sprint will walk students through adding advanced styling features such as a tabbed interface, modal dialog, and advanced rules to ensure that a blank to-do is not added.

**📕Feature: Advanced Web App Styling**
1. [**📖 Add completed checkbox and due date details to main list**](/Track_1_ToDo_App/Sprint-07%20-%20Advanced%20Styling%20Your%20Web%20App/Feature%201%20-%20Advanced%20Styling/User%20Story%201%20-%20Add%20Completed%20Checkbox.md)
2. [**📖 Add a tabbed interface to show different views**](/Track_1_ToDo_App/Sprint-07%20-%20Advanced%20Styling%20Your%20Web%20App/Feature%201%20-%20Advanced%20Styling/User%20Story%202%20-%20Add%20Tabbed%20Interface.md)
3. [**📖 Prevent User from adding blank task and limit characters**](/Track_1_ToDo_App/Sprint-07%20-%20Advanced%20Styling%20Your%20Web%20App/Feature%201%20-%20Advanced%20Styling/User%20Story%203%20-%20Prevent%20User%20from%20adding%20blank%20task.md)
4. [**📖 Confirm before deleting a task**](/Track_1_ToDo_App/Sprint-07%20-%20Advanced%20Styling%20Your%20Web%20App/Feature%201%20-%20Advanced%20Styling/User%20Story%204%20-%20Confirm%20Delete.md)
5. [**📖 Show spinner when loading recommendations**](/Track_1_ToDo_App/Sprint-07%20-%20Advanced%20Styling%20Your%20Web%20App/Feature%201%20-%20Advanced%20Styling/User%20Story%205%20-%20Show%20Spinner.md)

### Sprint 8 - Deploy to the Cloud
⏲️ _Est. time to complete: 60 min._ ⏲️

This sprint is designed to help students deploy the To-Do application to the cloud.  The sprint will walk students through deploying the To-Do application to the Microsoft Azure cloud.

**📕Feature: Deploy to Azure**
1.  If you are in the "_Everyone Can Code Event_" then please follow this user story: 
    - [**📖 Deploy To-Do App to Azure - Shared Subscription**](/Track_1_ToDo_App/Sprint-08%20-%20Deploy%20to%20the%20Cloud/Feature%201%20-%20Deploy%20to%20Azure.md/User%20Story%201%20-%20Deploy%20to%20Azure%20-original.md)

    If you are doing this exercise with your own subscription then please follow this user story:
    - [**📖 Deploy To-Do App to Azure - Own Subscription**](/Track_1_ToDo_App/Sprint-08%20-%20Deploy%20to%20the%20Cloud/Feature%201%20-%20Deploy%20to%20Azure.md/User%20Story%201%20-%20Deploy%20to%20Azure.md)

> [!CAUTION]
> Please note that once **your to-do application** is deployed to the cloud it **is running on the public internet and is accessible by anyone that has the URL to view and/or edit the information.  So, please do not put personal items in your to-do list**.   We would also **highly recommend that you setup security on the website**. You can enable this through the next user story.

2. [**📖 Setup Authentication**](/Track_1_ToDo_App//Sprint-08%20-%20Deploy%20to%20the%20Cloud/Feature%201%20-%20Deploy%20to%20Azure.md/User%20Story%202%20-%20Setup%20Authentication.md)

<br/>



<br/>

🎉 **Congratulations!**  You have completed the **Everyone Can Code** To-Do application track!!!   We hope that we "**Lit Your Fire for Coding**" and that you are excited to continue on your coding journey!

### Bonus Activities
Are you still looking for additional ideas on how you could continue to learn?  We have defined some "homework" scenarios that you can work on after this training.  These are just suggestions and would definitely encourage you to come up with your own ideas as well

- **Multiple lists per user** - Update the application to allow a user to store multiple lists underneath their account.
- **Mulit-tenant** - Update the application to allow different users to log in and see their "own" lists.
- **Different Authentication Provider** - You can experiment with setting up different authentication providers for the website. At the time of this repo being created there are providers for Facebook, Google, Twitter, GitHub, Apple, and OpenID Connect.
- **Migrate to a NoSQL database** - Migrate your backend storage from SQL to a NoSQL database like CosmosDB.
- **Create an API layer** - Create an API layer between the Web App and the database so that your to-do list can be automated by other scripts and/or programs beyond just the user interface. 

Want to continue using Azure after this event.  You can sign up [here to get started](https://azure.microsoft.com/en-us/free/) with a free Azure account.

<br/>

### Where to learn more

Still interesting in learning more about coding?  Check out the [**Where to Learn More**](/Track_1_ToDo_App/Where%20to%20Learn%20More.md) section for more resources on coding and building applications.