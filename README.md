<h1>Milestone Project 3</h1>

<h2>What I’m doing</h2>
<p>What I’m doing for this project is a recipe website. Going to have 5 pages for the app, a home page, recipes page, add recipes page amend recipes page and an edit recipes page. I’m going to use Python and MongoDB for the CRUD interactivity on this website, for this idea it makes more sense to use this as it’s a document orientated database as it’s going to store different documents of recipes. MySQL wouldn’t be as practical as I don’t require any relationships between databases just display the raw information.</p>
<h2>Pre-Production Planning</h2>
<h3>Balsamiq Wireframe</h3>
<p>I have created a wireframe before even creating the git repository so I have an idea on what I am creating. I created 5 pages with a webpage and mobile view, they are simple designs but I took time putting them together as I wanted a smart and simplistic look for this project as the ideal customer for this product will be for anyone of any age looking for recipes they want to store or look up so a complicated design could be daunting for users. I will most likely evolve the design as I go through the production of the app but it won’t stray far from this design as I’m really happy with it. I didn’t decide on the colour scheme for this app but I want simple warm colours for it. I don’t want to have unnecessary information of this app want to keep it simple so it isn’t overwhelming for anyone using the app hence why I have a homepage which will consist of a brief description of what this app does and then links at the bottom and then on each page a subtitle of the page with maybe a line of text stating a little more into it but I don’t believe this will be necessary and will decide closer to the time of production. This currently isn’t in the wireframe as I don’t believe it’s required but a thought that came into play while I was writing this. If I decide later down the line to do another wireframe with a changed design there will be another section below this but in current standing, I don’t think this will happen.</p>
<h3>Frameworks</h3>
<p>I am very comfortable with Bootstrap and I’m more drawn to this but I feel like learning another would be more beneficial for me in for after the course when pursuing a career in development. In this section, I was taught Materialise which is another framework which offers the same features but in a different style to Bootstrap which I would like to play with. The only turn off that I’m having from Materialise is that a fairly recent Google Chrome update to this framework has broken some of the interactivity and for it to work you have to add additional Javascript which just makes more unnecessary work for me to do on the app. I’m going to look and read through the features that Materialise offer and depending on that decides if I will go for that framework.</p>
<h2>Python Implementation</h2>
<h3>Page Connectivity</h3>
<p>The first thing I setup was the page connectivity with flask. The first page I created was base.html and put the basic html page formatting in and them created index.html and linked the pages together. I put inside index.html a title which stated homepage and then went to app.py imported os, Flask and all the extra features I’ll be using redirect and url_for. Since I was here I also imported py_mongo and bson and commented them out until they were required. I then installed Flask, Flask-PyMongo and dnspython via pip3 and saved it to the requirements.txt. I figured since I was implementing this how I may as well add everything I know I needed since I was already at this part. I then set up the app variable which is required for flask then the “if” statement which provides the IP and port information with debug enabled. I first created the routing via flask with the app.route command and set up the on load page as well as the route to it so it can be navigated it from others, then ran the app and it loaded with everything rendered. I then copied and pasted the index.html change and changed the names of the files and the titles within them. Created separate routes for each of them so app.py and then went back to base.html. At this point, I have already added a navigation bar from materialise with all the required links and Javascript added to the file but I will go into more detail on that in the pages section. I changed the href entries from # to url_for('page-function') in the correct navigation tabs for desktop and mobile versions and then tested. Each page loaded and the desired page which you could tell was correct by the different titles and the URL at the top had the /’route’ that I selected for it. At this point, I was happy with this part of the functionality as everything was working as intended. I made one addition which was the logo to link to the homepage as this is good coding practise.</p>
<h3>CRUD Stage 1</h3>
<p>When doing this I didn’t want to confuse myself by adding all the fields instantly and trying to get it to work so, instead, I decided to have one value in the database which could be created, read, updated and deleted. I did this in sections by firstly getting the page to view the data then be able to add it; after that, I then figured out how to delete and then update it. For this, I went back through the videos on each of these sections so it was fresh in my head as well as have the code for the working task manager app which I created just before this project as the example in the lessons. I started by adding to the route the mongo database variable that I needed to pass over into the page and then I copied parts of the code from the task manager app and pasted it into my project, changed the variables and tested to see if it worked which it did. A lot of this part is copied and pasted as this mainly for testing reasons as I wanted to get the functionality working and know it’s working as quickly as possible. The design towards the end will be different with more materialise but amended by me instead of copied and pasted. Then did the same for the add recipe page by passing the mongo variable into the page so it knew where the database was located then made a second function which was to insert the data on that page into the database then redirect you back to the recipe page where it can be viewed. I used a similar function to the one used in the videos and task manager app as this was how it was taught me and I understood and knew how to use it in this format. Copied the form and one of the fields that I required to test this from the task manager. Linked the correct function amended the name value and saved the code ran the function and then tested and it redirected me to the recipes page with the extra data, then checked mongo and the value was also displayed there. Next, I started working on the amend page so I copied the form from the tasks page in the task manager with the two buttons as I like that format and wanted it in my application and wanted to see if I can get that working in my app. I removed the old linking so it didn’t break the page and replaced them with “#” as placeholders. I then created the delete function in the app. I first watched the video then went to it and built it without the task manager template and tried doing it from memory and got it right apart from thing which was I put delete instead of remove as the action. I doubled checked it against the task manager code and noticed that changed it and it started to work. At this point I was capable of creating reading and deleting information via the app and all I needed how was updating so that it what I focused on doing. I watched the videos regarding this section again to get an understanding of it then went through the task manager code on both the html and the python to understand it and then I copied the code onto the edit recipe page so I had the same layout and it saved me time typing it out when for this test I wanted to prove my page was cable of this. I removed the previous code which would break the page and then went to the app.py to get this working. This page was newly created as the only way its accessible is by this button so I have to create a new route function for this page. I created the app route made the mongo variable and passed the argument through with the link to the page. I also added the object ID so it could identify which object it was handling, I also did this on the delete function. I went to the app to test if it was linking and on press it went to the form and a title saying edit recipe. How I had that part done I now needed to create another route which would pass the data in this form into the mongo database so I copied the first line of the previous code changing the name of the route and as well as the variable cutting out the ‘find one’ part as that isn’t necessary for this. What I did is change it to update but used the same format as the video as it looks neater compared to one long variable. Added the object ID to this as one argument and then created the object value layout so the inputted data knows where is needs go. After that added the redirect so it sent you back to the amend recipes page. I went back to the template and added the url_for the update function as well as the object ID to the form action so it knew what to do on post and which object to do it too. I then amended the name for the text area form field so it knew which row it was editing. I also tested to see if it was pulling through the pre edit data by adding the {{object.row_name}} in between the text area tags which was appearing on the run of the app. At this point everything should be working so I created a value which was called “This” and then added edited it to say “This is a test” submitted it and the object was amended. At this point my app had full CRUD capability and now I just had add addition rows style it and make it usable for an everyday user. </p>
<h3>CRUD Stage 2</h3>
<p>Since I got the basic CRUD functionality at this point and I done all the testing to prove that it was working all I needed to do was add all form entries and link them up so it had a purpose as well as function. I started with going to materialise and adding the form to the add recipe page. I wanted a text area, input field and a selection box which I could use multiple times. I got the forms entries and added them to the form inside the page. Played with the sizing and got them positioned correctly and then decided to add the necessary python to get the code passing into mongoDB. The databases I previous created I now linked to the function so I could push the database entries as values for the selection boxes. When I added all the variables to the return route I then changed all the names in the forms to match the value names in the database. For all the selection boxes I created for loop to the databases that I wanted them to be linked to so it would display all the options. After I did this I ran the program app went onto the add recipe page all the selection boxes pulled through the options I chose which is what I checked first. I then filled out all the fields and wrote down what I chose added the recipe and compared the results with what is displayed in the database and they matched so the form was complete and all that needed now was styling. I then went onto sorting out the amend page as I wanted the exact same form format for simplicity within the app. Everything was already in place to get the data pulling through except the link variables in the function except the database links which I added. I then changed the form entries to display the inputted variables that you want to amend, It did this with if statements inside the for statements. I tested this by opening the edit page and compared the pulled through values against they all matched so I added to the function that I previous created to push the data. I added all the request form get objects so it knew what was in place to update what. With them added and changed all the values by increasing the numbers and difficulty by one as we as adding an exclamation mark to the end of all the text. I then checked the database and all the numbers increased by the value above and all words had exclamation marks on the end. I checked for a duplicate data entry which there wasn’t so I can confirm that it was working as intended. I then went to the recipe page and used two collapsible boxes for the display one containing all the information on what it is who it’s suitable for and timings etc. the second box contained the instructions as well as the ingredients  required to cook. I had a simple and clean look so I went with it. The first box had the recipe name as the title which stated what the recipe is and when opened it pulled through the difficulty, time to prep and cook, dietary requirements and if there is anything specific required to cook it. The second box had a static title which is instructions and ingredients with the instructions and ingredients inside. The final page for editing was the amend page which is linked to the edit page and the delete function. The idea I had for this changed from the original where the collapsible box contains the buttons instead of having duplicated information from the recipe page. It contained the edit button which takes you to the edit page and a delete but which on click opens a modal with a warning message stating this is about to be deleted and if you click close nothing happens except the modal closing and if you click delete it would recipe permanently. With all this done that it the CRUD functionality completely implemented and working as indented.</p>
<h2>Design</h2>
<h3>Home Page</h3>
<p>The home page is just an introduction to the app nothing too fancy with no special features just a static welcome page. I had a title which was a welcome and below it had a welcome message I then did a short section on what each page does to act as brief instructions to the app. There is a disclaimer at the bottom saying please don’t vandalise other recipes on the app. There are three images below that which have titles and are clickable links to different pages on the app. Apart from that the page title changes size when it shrinks and the image titles shrink also. The images on the page change from 3 in a row to a full row on top of each other with their titles. Throughout the app there is a mixture of the grid system between materialise and bootstrap as the materialise system seemed to play up now and then which confused me as they’re pretty much the same thing. The colour scheme I went for is what I pictured in a bakery warm light browns with different shades to contrast the different parts of the page I tried to set a generic sizing for each title by setting h1, h2, h3 with specific styles. The font I went for the titles was a smart hand writing type of style which I liked and personally gave it a homely personal touch. For the bulk of the text I used a different font which I thought looked good and suited the style. I chose to go with white font almost over the entire site as it contrasted well with the colour scheme. </p>
<h3>Recipe Page</h3>
<p>The recipe page follows the same colour scheme as the rest of the site with the browns and white text I used the title font in the collapsible containers for the titles in white and inside the text is black as the white seemed too bright for the background so that’s the reason for that design choices the containers are the darker brown and the content on the inside are the lighter shade. I added a div to the bottom which is a lighter brown as a separator between the different recipes it is in the for loop so it will appear on every recipe entry. I added some additional python to this page where if you leave the specific utensils blank it places a message saying “Nothing Specific Required” instead of it being blank as this is the most optional option in this example and least likely to have an entry. For the first collapsible the divs are on top of each other with the variable name to the left with the value on the right. In the second collapsible it has a title with a larger font and then instruction/ingredients stated below the title. </p>
<h3>Add & Edit Page</h3>
<p>I’m grouping these pages together for a description as they are identical except for the function the do. I used the form components from Google Materialise for the form as I have previously used them and I liked the look of them. So I got a drop box, text area and a single line text box. I had the same colour scheme as the over pages to keep a style the same across the app. Same fonts with the same previous pages following the same styles with titles have the hand writing style but the text in the selection boxes kept their original font as it suited the input fields and was clear to read. I amended all the dividers and I tags show there static colours are all white. I left the active effects the same as I really liked the green change it really highlighted that you just interacted with the selection box. The selection boxes all took up half of the container but when it is on mobile the final selection box becomes the full row for two seasons it isn’t ridiculously big and suites the form on a mobile and the sentences in the dietary requirements box fits better. The font inside the selection boxes also shrinks on mobile so you can see it more clearly. Originally I wanted to add an image in the form of a hyperlink which you add and it goes in links to a source part of an image tag. I had problems getting it too work all the time and since it’s just an extra nice to have feature I thought it wasn’t entirely needed and when I tested it with my parents it confused them without any explanation and even when I wrote one in the didn’t seem to paste it in properly. When I learn how to upload jpegs to a document I’ll then do this future either coming back to this project as it’s nice to add or for future projects where it would be necessary. The button at the bottom of the page which is linked to the submit function I amended the colours for it. I had the button colour the same as the background as it contrasts well with the darker brown form container with white font. When you interact with it fades to an off white/brown colour with black text.</p>
<h3>Amend Page</h3>
<p>The amend page is a very simple page which consists of single collapsible containers which has a title of the recipe you’d like to amend and inside the collapsible part there are two button one deletes one edits. The colour scheme of the delete is the same colour as the dark brown that the container uses to contrast with the light brown background. When you interact with it, it gets darker and on click it opens up a modal that has a title and a sentence pretty much warning you’re about to delete a recipe. Close shuts down the modal and delete closes the modal and permanently deletes the recipe. The edit button is a grey colour with white text. Both buttons use the text font style I chose. On the hover of the edit button the colours swap so the background goes white and the text goes grey. There is another div at the bottom which is the light brown used as a divider to split up the recipes on this page. </p>
<h2>Testing</h2>
<p>For the testing I covered the majority of it in the CRUD breakdown part but I first started by implemented the CRUD capabilities for one entry per action. Firstly I created the database and linked it to the app, I then put the necessary code in place for it to display. I then added the data to the actual database on MongoDB and reloaded the application and it pulled through. The next step was to add the capabilities to add data directly from the app. I went back and forth over the video unit and the previous practise project to figure out what I needed. I then added it to the app and made the necessary changes on the python and html file. For the texting period I copied the form from the previous project so I could quickly text for functionality. When I proved I got it working I build the second one in line with it so I could duplicate what was one the second new with the working one. I then implemented edit and I copied the form from the edit page on the previous product made the changes to the function in python and corrected the target name and route so it could communicate I always added exclamation marks to the end of the words for testing, small but noticeable change. After I made the changes I tested and the exclamation mark came through but first test made a new database entry I didn’t change the url_for to point to the correct function. Made that change and it started working. The next was simple which was the delete function made the changes to a button on the amend page by adding the delete button with the delete function attached and it all started working. After this I added all the other form entries linked up the extra databases for options testing part by part seeing if it was pulling through and then seeing if everything submitted which it did exactly as I expected it too. The second stage of testing was for users I got my parents my brother and sister to test all the features to see it could be used easily. They all managed to add, amend, view and see the data that they implemented without any issues. I didn’t test the HTML with the HTML validator this time as I was using base.html which contained the head I believed it would all fail. </p>
<h2>Deployment</h2>
<p>The method I’m using to deploy my project is Heroku. I wanted to add a little more of a professional touch to this project by hiding the environment variables as this is standard when working in the real world so I did my final submit git pushed it too my GitHub double checked everything making sure I was happy with what I produced and then started the procedure. Decided to name the app in Heroku the name of the product form the start which was Lozzy’s Lovely Recipes. I did the Heroku login which connects me to the service made sure I had all the requirements up to date and the Procfile and then did the Heroku master submit. I left it a little while for it to fully go through and then added all the variables that are required to run the service. So I added the IP as 0.0.0.0, Port 5000 and finally the MongoDB variable so it knew how to find the database. Adding the database here keeps the passwords for the database protected from the outside world. I opened the project in Heroku and tested to see If everything was running and working as intended. I could confirm that everything was working as I wanted and was happy to submit it as my completed project. </p>
<h2>Final Changes</h2>
<p>I made a change to the app which I luckily had the chance to do as it broke the delete function. The modal I had added to the delete function broke the function where it only deleted the first database entry instead of the selected one. I believe this is due to the object ID not being passed onto the modal so therefore loses which one it’s deleting so it resolves to the first database entry. I removed the modal as it caused this problem and decided to submit without it. I really wanted to have this feature in the app but due to time restraints I thought it would be best to submit without and have the functionality working properly. I’m going to look into this as well as speak to my mentor and figure out what I did wrong with this.</p>
<h2>Conclusion</h2>
<p>Overall I have enjoyed this project I had a lot more understanding of python compared to Javascript which I struggled with. The Python language is easy to read, understand and implement and I’m looking forward to continuing to use it in the future and pushing its capabilities. I liked using a different framework this time for the project Google Materialise which makes me interested in looking into others in the near future and seeing what I can use from them systems. I did use some bootstrap but the majority of the framework was Materialise. I feel like since the first project my understanding of HTML and CSS have gotten great a lot faster than I expected. I know different tricks and tips to bend styles to the exact way I want them. I didn’t use any own built javascript for this project as I believed that one it wasn’t necessary and would of gone overboard on the simplistic design I was going for and two this project was testing my abilities with python so I really didn’t feel like over complicating this and adding more work than what was required for this. Overall I’m very happy with how this has turned out I didn’t expect to pick it up so quickly and use this with ease. I know that I’ve only just scratched the surface and have a stupid amount more to learn but it was nice to be able to get through this without much assistance feels like I’m making great progress in the way of becoming a developer.</p>

<h2>external rescources</h2>
<h4>Home page image 1</h4>
<p>https://www.google.com/search?q=recipe&rlz=1C1CHBF_en-GBGB758GB758&sxsrf=ALeKk01ORbEQfob-20wydVHE2t1q0oqOVQ:1589913820563&source=lnms&tbm=isch&sa=X&ved=2ahUKEwiM4_3DysDpAhVKXsAKHbpKAsAQ_AUoAXoECBAQAw&biw=1920&bih=937#imgrc=FvVdI80i3MlbPM</p>
<h4>Home page image 2</h4>
<p>https://www.google.com/search?q=writing&tbm=isch&ved=2ahUKEwiw_q7Gy8DpAhVMSxoKHcnVCcoQ2-cCegQIABAA&oq=writing&gs_lcp=CgNpbWcQAzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzoECCMQJzoCCABQm4IBWPuKAWDIjAFoAHAAeACAAT2IAXeSAQEymAEAoAEBqgELZ3dzLXdpei1pbWc&sclient=img&ei=7SnEXvDTPMyWacmrp9AM&bih=937&biw=1920&rlz=1C1CHBF_en-GBGB758GB758#imgrc=GT64ffdZNt9hxM&imgdii=vDZ3bPEozWf2FM</p>
<h4>Home page image 3</h4>
<p>https://www.google.com/search?q=editing+&tbm=isch&ved=2ahUKEwjI3sWbzMDpAhVVPhoKHaBHAPUQ2-cCegQIABAA&oq=editing+&gs_lcp=CgNpbWcQAzIECCMQJzIECCMQJzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQzIECAAQQ1DQKljQKmD4ZGgAcAB4AIABM4gBM5IBATGYAQCgAQGqAQtnd3Mtd2l6LWltZw&sclient=img&ei=oCrEXsiOJtX8aKCPgagP&bih=937&biw=1920&rlz=1C1CHBF_en-GBGB758GB758#imgrc=mRkk-l1ae1ea7M&imgdii=R0BKCXF64Myd_M</p>