# 📖 User Story: Personalize Web Application - Step-by-Step
⏲️ _Est. time to complete: 20 min._ ⏲️

## User Story

*As a user, I want to be able to customize the look and feel of my web application*

## 🎯Acceptance Criteria:
- The web app should have a custom title that reflects the user's preferences.
- The web app should have a custom color scheme that reflects the user's preferences.
- The web app should have a background picture for the website.
- The web app should have a custom favicon that shows up in the browser tab
- The interface should look something like this:

    ![outcome5](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/outcome-S02-F02-US02.png)

## 🎓Know Before You Start
no resources at this time

## 📋Steps

In order to complete this user story, you will need to complete the following tasks:

### Open Visual Studio Code
Open Visual Studio Code (either locally in the project directory you setup or through your Codespace). Visual Studio Code should have your completed solution from the end of Sprint-01 or if you prefer you can use the starting reference application from [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us01/) by copying it over into your local directory or Codespace.

### Updating Titles

#### 1. Customize the Title
We first will customize the title of the web application. Go into your `index.html` file and update the `<title>` tag to reflect a title unique to you. For example, you can change the title to _My To-Do List_ or _Sarah's To-Do List_ or whatever you like.

```html
<!-- Example of where to look in the index.html file, do NOT copy/paste this code directly into your project as it does not have all of the sections underneath the <head> tag that are in your file  -->
<head>
    <title>My To-Do List</title>
    <!--...other code-->
</head>
```

The `<title>` tag in the HTML document sets the title of the web page in the browser tab. By customizing the title, you can provide a personalized touch to the web app. 

<br/>

#### 2. Customize the Heading
Let's also change the name of the web app displayed as part of the home page. Replace the `<h1>...</h1>` tag with the following code: 

```html
<br/>
<br/>
<div class="h-100 p-5 bg-body-tertiary border rounded-3">
    <h1>My To-Do List</h1>
</div>
<br />
```

This will change the heading of the web app to "My To-Do List" and provide a more personalized experience for the user. The classes `h-100`, `p-5`, `bg-body-tertiary`, and `border rounded-3` are Bootstrap classes that add padding, background color, and border to the heading.

<br/>

### Customize Color Scheme
In this section, we will customize the color scheme of the web app to reflect the user's preferences.

#### 1. Create a Custom CSS File
We will need to add a custom CSS file so create a new file called `style.css` in the `static/css` folder of your application.  If these folders do not exist you will need to create them first.  

![Create CSS File](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/NewFile-S2-F2-US2-01.png)

> [!NOTE]
> If you are using Codespaces, you will want to create the following folders `/static/css/` in the root of the repository.

#### 2. Add Custom Color Scheme
Add the following code to the `style.css` file to define a custom color scheme for the web app:

```css
body {
    background-color: blue; 
    color: white;  
    font-family: Arial, sans-serif;
}

h1 {
    color: blue; 
}
```

This code sets the background color of the body to blue and the font color to white. It also sets the font color of the heading to blue to ensure it is visible against the container background color. You can experiment with different colors and styles to create a custom color scheme reflecting your preferences.

<br/>

#### 3. Link Custom CSS File to the HTML Document
Link the custom CSS file to the HTML document by adding the following code within the `<head>` tags in your `index.html` file right after the link to the bootstrap CSS file:

```html
<link rel="stylesheet" href="{{ url_for('static', filename='css/style.css') }}">  
```

This code links the custom CSS file to the HTML document, allowing you to apply the custom color scheme to the web app. The `url_for('static', filename='css/style.css')` function generates the URL for the static file based on the file name provided.

<br/>

#### 4. Run the Application
Give it a try! Open the web app in your browser to see the changes you made. You should see the updated title, heading, and color scheme reflecting your preferences.

![Customized Web App](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/RunApp-S2-F2-US2-01.png)

Feel free to experiment with different colors and styles to create a personalized look and feel for the web app.

<br/>

### Add Background Picture
In this section, we will add a background picture to the web app to enhance the visual appeal of the user interface.

#### 1. Create or Use a Background Picture
Next, let's add a background picture to the web app. You can use the existing picture we have pre-created using [Microsoft Designer](https://designer.microsoft.com/) (which has been generated by AI using DALL-E) and can be seen below or if you like you can create a picture of your own by taking advantage of generative AI.   

If you want to use the pre-created image you can find it in this [**directory**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us02/static/images/). Save it locally to your PC or Mac. If you need instructions on how to download this picture to your local machine you can find them [**here**](download%20image.md)

Or to create your own image using **Microsoft Designer** please follow the instructions [**here**](./Using%20Microsoft%20Designer.md)

![Background Image](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us02/static/images/Designer02.jpeg)

<br/>

#### 2. Save the Background Picture
Whether you created your own picture or are using the pre-generated background picture, you will need to copy the downloaded image to the `static/images` folder of your application. If the folder does not exist, you will need to create it first.  Ensure you name the file `Designer02.jpeg` to match the name we will be using in the CSS file. 

![Copy Image](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/CopyImage-S2-F2-US2-01.png)

#### 3. Update the CSS File to include the Background Picture
Replace the code in your `style.css` file with the following code to set the background image of the body:

```css
body {
    color: darkslategray;  /* default font color */
    font-family: Arial, sans-serif;
    background-image: url("../images/Designer02.jpeg");
    background-repeat: no-repeat;
    background-position: center;
    background-size:cover;
}

label {
    color: white
}

h1 {
    color: darkgray; /* font for the h1 header*/
}

.list-group-item {
    color: #333; /* dark grey */
}
```

This code sets the background image of the body to the image you saved in the `static/images` folder. The `background-image` property specifies the URL of the image, and the `background-size: cover;` property ensures the image covers the entire background. The `background-position` property centers the image and the `background-repeat: no-repeat;` property prevents the image from repeating.
    
This code also sets the font color of the list items to dark grey to ensure they are visible against the background image. The title and body font color are set to white to ensuring they too are visible against the background image.

You can experiment with different colors and styles to create a custom look and feel for the web app.
    
<br/>

#### 4. Run the Application
Save the changes to the `style.css` file and refresh the web app in your browser. You should see the background image displayed on the web app providing a more visually appealing experience for the user.

![Background Image](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/RunApp-S2-F2-US2-02.png)

<br/>

### Add Custom Favicon
In this section, we will add a custom favicon to the web app to enhance the user experience. The favicon is a small icon appearing in the browser tab next to the title of the web page.

#### 1. Add a Custom Favicon to the application
Let's add a custom favicon to the web app. You can create a custom favicon using an online favicon generator or by using an image editing tool like Photoshop or GIMP.  For this exercise, you can use the favicon provided in the `images` folder of the source code. Please copy the `favicon.ico` from [**here**](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us02/static/images) file to the `static/images` folder of your application. If the folder does not exist, you will need to create it first. If you need help downloading the file, you should follow the instructions above for downloading the background image. 

![Copy Favicon](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us02/static/images/favicon.ico)

<br/>

#### 2. Update the HTML Document to Include the Favicon
You will need to update the `index.html` file to include the favicon. Add the following code to the `<head>` tag in your `index.html` file:

```html
<link rel="icon" type="image/x-icon" href="{{ url_for('static', filename='images/favicon.ico') }}">
```

This code links the favicon image to the HTML document, allowing you to display a custom icon in the browser tab. The `url_for('static', filename='images/favicon.png')` function generates the URL for the favicon image based on the file name provided.

<br/>

#### 3. Run the Application
Save the changes to the `index.html` file and refresh the web app in your browser. You should see the custom favicon displayed in the browser tab next to the title of the web page.

![Custom Favicon](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/images/RunApp-S2-F2-US2-03.png)

<br/>

> [!NOTE]
>To stop the server simply hit `CTRL-C` in the terminal window where the web server is running.

<br/>

<br/>
🎉 Congratulations! You have now updated your web application to have a more personalized look and feel with a custom title, color scheme, background picture, and favicon. This will provide a more engaging and visually appealing experience for the user. 

<br/>

> [!NOTE]
> 📄For the full source code for this exercise, please see [here](/Track_1_ToDo_App/Sprint-02%20-%20Web%20Application/src/app-s02-f02-us02/).

<br/>

[🔼 Home ](/Track_1_ToDo_App/README.md) | [**◀ Previous user story**](User%20Story%201%20-%20Add%20Basic%20Styling%20to%20the%20Web%20App.md) | [**Next user story** (in next sprint) ▶](/Track_1_ToDo_App/Sprint-03%20-%20Database%20Integration/Features%201%20-%20Shift%20task%20storage%20to%20database/User%20Story%201%20-%20Move%20from%20File%20Storage%20to%20database.md)
