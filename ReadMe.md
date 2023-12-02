# How to convert a web from HTML/CSS/VanillaJS to React JS ?

### Create a React app using 'cra' command
    Open Terminal:
        $ cd Desktop/
        $ npm npx create-react-app@latest 'ourApp'
        $ cd 'ourApp'
        $ code . (app will be open to VS Code)
        Open the integrated Terminal
        $ npm install
        $ npm start
        
    Now lets dive in:
        - Take a look at SRC Boilerplate
        - Removing unnecessary things

### What to keep for our React App?
        - App.js 
        - index.js
        - index.css

### Structure of our App
        - Public/index.html
            - CDN of Font Awesome
        - CSS code
            - Copy all CSS code from your 'html website' and paste into 'index.css' within 'src'
        - Images for our App
            - Create a folder 'images' and copy from your 'html website' and paste to 'images' folder 
        - Components
            - Here we can keep all 'html code' in one file (App.js) so is not recommended.
            - We are going to create components for each section
            - We have created for each section one Component.
                - Compponents are:
                    - About.js
                    - Footer.js
                    - Hero.js
                    - Navbar.js
                    - Services.js
                    - Title.js
                    - Tours.js

                - We are going to use ES7 snippet to create automatically and exported our component. 
                    - rafce inside of each file, and this will create the component with the name of the file. ()

        - data.js (refactoring repeated code)
            - Here we are going to store all our code
            - Array of object
            - Iterate over data
            - Destructuing
            - Rendering Data
            - Inject dynamic data
            - Set up props for different sections

### Deployment
        - We are going to host our app into Netlify
            - Issues
                - Netlify treats "warnings" as "erros" and will not let us to build our site, so we have to make sure that we dont have warnings.
                - Some warnings are:
                    - Single hashtangs '#' or links
                        - Easy fix, just add the page you want to go, ie: #about or #home ✅
                        - "_target" attribute on anchor tags
                        - Easy fix, just add "rel='noreferrer' " after the "_target" attribute ✅
                        - Another fix add it twice "rel='noreferrer noreferrer' 
                        - Another fix is :
                            - Go to Problems right click on each problem and click 'fix and rest of the sentence' and automatically will be fixed
            - We have two ways to deploy our App.
                - Manually deployment
                - Import from Github

###  We are going to use 'Continuous Deployment'
        - Go to Netlify
        - Sign Up/In with Github
        - Select Import from Github
        - Deploy
            - See logs for errors
            - We can change the name

### Benefits of Netlify
        - Dont need to keep project locally
        - Automatic builds
            - Host your local App into Github first using Git
            - After you have hosted your app in github, you can delete your local app.
        - Now lets make a change in our app. Steps:
            - git clone
            - run locally first, $ npm i or npm install to install all dependencies.
            - npm start (If you are using Linux/Mac your can type $ npm install && start, eventually Im using Windows so I have to split commands)
        - Now make a simple change and push it to github.
            - Make sure that the server is running
            - Use commands by opening a new Bash/Terminal/Cmd/Powershell or VS Code GUI to your left.
        - Go to Netflify App and just refresh the page.
            - Changes are made automatically
            - If something goes wrong, Netlify will stay with the previous deployment. (We have a change to see new errors, this will make good developers xD), check logs for errors, Netlify will explain that.

### Warning "Gotcha"
        - Netlify will run "npm run build" for us after we have imported our App.
        - We we will see an error like this env "CI" is set true, but in 'development' mode our command is working.
            - This is a easyfix:
                - Go to 'package.json' under scripts add this line ' "CI= react-scripts build" '
            
            From this:
            "scripts": {
            "start": "react-scripts start",
            "build": "react-scripts build",
            "test": "react-scripts test",
            "eject": "react-scripts eject"
        },

            To this: 
            "scripts": {
            "start": "react-scripts start",
            "build": "CI= react-scripts build",
            "local-build": "react-scripts build"
            "test": "react-scripts test",
            "eject": "react-scripts eject"
        },

    Explanation:
    - "react-scripts build" is for our local build
    - "CI= react-scripts build" is for Netlify environment.

    