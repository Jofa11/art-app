# [Creativity Canvas](https://unruffled-rosalind-0724d0.netlify.app/)

### A super fun drawing app that let's you stretch those artistic muscles!

### Home Page
A brief intro to the site and a button that sends you to the canvas page.
![Home Page](https://user-images.githubusercontent.com/45057976/143188793-b4a08be1-26bb-475c-9b81-309f8ae5da76.png)

### Canvas Page
The main page of that app. Here lives the canvas with color picker and line width input field. There is a clear canvas button and a link back to the landing page.
![Canvas Page](https://user-images.githubusercontent.com/45057976/143188669-39bcbdbe-8798-4fb6-b87a-9cf9d2e2d386.png)

### Footer
Links to my Github, LinkedIn, Twitter, and portfolio pages
![Footer](https://user-images.githubusercontent.com/45057976/143189845-2394147b-c7f9-4c9e-bfa1-57298e93bff7.png)

### Wireframe
#### Homepage
![Wireframe-Homepage](https://user-images.githubusercontent.com/45057976/143190483-dabe917b-e5d6-4afb-bb03-44c326c217e8.png)
#### Canvas Page
![Wireframe-Main](https://user-images.githubusercontent.com/45057976/143190494-655204b7-765f-4498-ae0d-b427226259d2.png)
)

### Code Snippets
This Javascript code, in Vue.js, handles the dynamic width and height of the canvas. It resizes the canvas when it loads.
![code](https://user-images.githubusercontent.com/45057976/143191447-cf5cda47-f562-488b-8fb9-8760d06400d5.png)

This function sets all the properties of the canvas with the dynamic variables and begins drawing.
![code](https://user-images.githubusercontent.com/45057976/143191535-f6f100e0-e4bb-4d43-9a66-00ca12330abe.png)

The changeHandler function retrieves the values from the inputs and sets the variables to those values. The clearCanvas function does just what it sounds like, gives us a blank slate to start over again.
![code](https://user-images.githubusercontent.com/45057976/143191599-e6962b6b-ce6b-4cbd-b1a7-5bf5ced10b36.png)

I was having trouble getting the canvas to resize without manually refreshing the page. This function inside the Vue lifecycle hook takes care of that as you resize your screen.
![code](https://user-images.githubusercontent.com/45057976/143191613-d0929eb8-ae03-49d8-b335-989d7c9c4c0c.png)

### Technologies Used
Creativity Canvas was built as a Vue.js application. I recently started learning Vue, migrating from React. Both frameworks are great, but I'm starting to favor Vue a bit more. It is so intuitive and easy to understand, and you are using mostly plain HTML in the templates. Styling for this app was achieved with vanilla CSS. I opted not to use a framework to give it a custom feel. I used Github for version control and the site is hosted on Netlify. The icons on the site are from [icons8.com](https://icons8.com/).

### Contribution Guidelines
If you have some cool ideas and would like to contribute, I will definitely consider it. Fork, clone, and send an issue if you have any proposed improvements to the app. This app is built for learning purposes, but I do appreciate any feedback. Thanks for checking it out.
