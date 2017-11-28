#Chicken Bus Design Doc
##Architecture
ChickenBus will have 3 main components: a web front-end, a mobile front-end, and a backend for accessing a database of bus routes. The web front-end will be the graphical interface that will tell users about the application while also allowing them to search for bus routes in Nicaragua. The front-end will consist of inputs for searching for routes as well as a map that will display any searched routes.
The mobile application will follow the same form as the web application. It will make requests to the same backend and database as the web app. The mobile application development will focus on creating a React Native application that will allow us to traget both android and ios development.
The backend will be the cornerstone of the project. It will contain the database that we will use to keep track of routes and will also contain the api that we will use to access our database. The api will be designed with the idea of eventually making it accessible outside the scope of ChickenBus.
###Modules
- TypeScript: A superset of JavaScript that add type casting to JS variables. Also enables intellisnense and Object Oriented principles to be applied to web development. Will be used as a way of keeping track of different component props on the front end.
- Webpack: A bundler that will compile and combine all JS and TS (TypeScript) files into one dist file that will be served to the user. We will also use the webpack dev server for front end development due to its ability to "hot reload" allowing changes to be made without the need to restart the dev server.
- React: A JS library that allows for the creation of components that represent reusable objects that can be used to build front end. React will allow for a front end that can be easily changed and built upon by relying on modularized design.
- Node.js: A technology that allows for a backend to be run using only javascript. We will use node package manager as a way of referencing external code bases.
- Express: The backend framework we will be using. It will rely on Node as its language, but the structure will adhere to the express framework.
###Processes
- No concurrent processes being used. Will update if needed.
###Data
- Routes: Routes are stored as geoJSON which are stored as JSON with different attributes regarding route information such as stops or times.
- Users: We store users in our database to kepe track of who is able to add routes to the databse.
##Module Definitions
- Frontend: All front end component definitions can be found in the components folder [here](https://github.com/KyleMartin95/ChickenBus-Frontend/tree/master/src/components). Each component has a file called 'componentName.props.ts' that will list out interface definitions for its methods, stylings, and and properties.
##Data Definitions
- Backend: Our data definitons can be found in the images attatched to the design architecture file.
##Design Decisions
- Development will focus on the web application and move to mobile after the backend is in a stable state.
- Typescript was used over Javascript due to its complementing nature with React. We can have each component be cast as its own unique class which will help with debugging due to intellisense.
- We will be using React Native for the mobile app. This is due to the quick development cycle we can achieve by not having to create native apps for both ios and andriod in seperate codebases. We will instead be able to use one JS code base to achieve a functional mobile app for both platforms.
- The database will take priority in terms of development decisions. Our apps value lies heavily with the databse.
##Notable Changes
###10-24-17
Reworked entry gate page to display routes upon preview button or add route button being clicked. More work will need to go into teasing out functionality once the routes are able to be manipulated on the google map. Some questions going forward will be how to deal with the location input boxes when their corresponding map marker is dragged to another location. Will the text in the box become blank or will we need to update the text?
###11-28-17
Major changes have included the decision to no longer try to display entire routes for the time being. We will instead focus solely on displaying route information and "hops" between stops. We will be using arcsto connect different origins and destinations.
###11-28-17
Major changes have included the decision to no longer try to display entire routes for the time being. We will instead focus solely on displaying route information and "hops" between stops. We will be using arcsto connect different origins and destinations. We also now have a bulk data import using a csv as well as the begginings of a database CRUD gui.