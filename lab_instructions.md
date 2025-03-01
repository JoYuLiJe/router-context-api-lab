# React OMDB Movie Search Application

Build a React application that allows users to search for movies using the OMDB API.

## Table of Contents

- [Setting up the Project](#setting-up-the-project)
- [Developing the Application](#developing-the-application)
- [Conclusion](#conclusion)

---

## Setting up the Project

### 1. **Fork and Clone**:
Begin by forking the existing React project from the given repository. 

Once you've forked the repository to your own GitHub account, clone it to your local machine
and open in VSCode.


### 2. **Install Dependencies**:
The repository might have some dependencies that are required for the project to run smoothly. Install these packages to ensure everything works as expected:

  ```bash
      npm install
  ```
Additionally, the project uses two other packages: axios for making HTTP requests and dotenv for handling environment variables. To install them, open a second terminal in the project repo and run the following command:

  ```bash
      npm install axios dotenv
  ```

### 3. **Environment Variables**:
   - Register at the [OMDB website](http://www.omdbapi.com/apikey.aspx) to get your API key.
   - Create a `.env` file in the root of your project.
   - Store your API key:

     ```
     REACT_APP_OMDB_API_KEY=your_api_key_here
     ```

Environment variables prefixed with `REACT_APP_` are embedded into the build at compile-time.

---

## Developing the Application

### 1. **Setting up API Utility**:

   - Open the `api.js` found within the `services/` directory.
   - Here, write the two `axios` functions that will communicate with the OMDB API. Use your environment variable for the API key. The declarations and parameters have been given to you. 

### 2. **Setting up Context**:

   - Navigate to `MovieContext.jsx` inside of `src/`.
   - Define and export a React context for storing the search term and search results. This allows for global state management, making data accessible to any component.

### 3. **Building Components and Pages**:

#### Components:

##### 1. **SearchBar** (`components/SearchBar.jsx`):
   - This component contains an input field and a button.
   - Users type a movie's name or keyword into the input field.
   - The search should be initiated when the button is clicked or the enter key is pressed.

##### 2. **MovieItem** (`components/MovieItem.jsx`):
   - This component is responsible for displaying a single movie result.
   - It should accept a movie object as a prop and display essential details like the title, year, and poster image.
   - The movie's title or image can be made clickable to navigate to its detailed info.

##### 3. **MovieList** (`components/MovieList.jsx`):
   - This component will display a list of movies based on the search term.
   - Use the `MovieItem` component to render each movie.
   - If no movies are found, display an appropriate message to the user.
   - Consider showing a "Loading..." message while fetching the movies.

#### Pages:

##### 1. **HomePage** (`pages/HomePage.jsx`):
   - This is the landing page of the application. You can provide a brief description of the application or any other relevant information here.
   - It should also include the `SearchBar` to allow users to initiate movie searches.

##### 2. **SearchPage** (`pages/SearchPage.jsx`):
   - This page will display the search results.
   - It should prominently feature the `MovieList` component.
   - You can also incorporate the `SearchBar` at the top to allow users to refine or change their search.

##### 3. **MovieDetailsPage** (`pages/MovieDetailsPage.jsx`):
   - This page displays detailed information about a specific movie.
   - The movie's detailed attributes, like its plot, actors, ratings, etc., should be prominently displayed.
   - Provide a back button or link for users to return to the search results or home page.

##### 4. **NotFoundPage** (`pages/NotFoundPage.jsx`):
   - This page will be displayed if a user tries to navigate to a route that doesn't exist.
   - A simple message like "404: Page Not Found" should suffice. Consider adding a link to navigate back to the home page.



### 4. **Component Integration**:

   - Modify `App.js` to include your components.
   - Make sure to wrap any components that require access to the `MovieContext` within its provider.

### 5. **Styling**:

   - Add styling as required. You can create CSS files for each component or maintain a central `styles.css` file.
   - Ensure the user interface is intuitive and user-friendly.

### 6. **Testing**:

   - Once all components are integrated and styled, run the application:

     ```bash
     npm start
     ```

   - Test the functionality. Enter movie names, view the list, and check out movie details.

### 7. **Optional Enhancements**:

   - Implement pagination for viewing more search results.
   - Add error messages for failed API calls or no search results.
   - Enhance the design or add additional features as you see fit.

---

## Conclusion:

Congratulations! You've constructed a React movie search app using the OMDB API. You've learned about React context, `axios` for API requests, and environment variable management.

Next steps:
- Deploy your app for others to use.
- Expand with more features or integrations.
