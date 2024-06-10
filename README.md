#celebrity_details_web_application
# Celebrity Details Web Application
## Project Overview
The Celebrity Details web application is designed to provide users with comprehensive information about various celebrities. The application allows users to search for celebrity details, view their profiles, and access additional information such as biographies, filmographies, and social media links. This project integrates multiple technologies and services to offer a seamless user experience, including Firebase for user authentication and data storage, and a third-party API for fetching celebrity details.

## Key Features
- **User Authentication**: Users can sign up for an account, log in, and access personalized features.
- **Celebrity Data Retrieval**: The application fetches real-time celebrity details from a third-party API.
- **Profile Viewing**: Users can search for and view detailed profiles of celebrities.
- **Educational Content**: Provides biographies, filmographies, and other relevant information about celebrities.
- **Responsive Design**: Ensures a seamless user experience across different devices.

## Technologies Used
- **Frontend**: HTML, CSS, EJS (Embedded JavaScript Templates)
- **Backend**: Node.js, Express.js
- **Database**: Firestore (Firebase)
- **Authentication**: Firebase Authentication
- **API Integration**: API Ninjas (for celebrity details)
- **Session Management**: Express-session

## File Structure
### Frontend Files
- **home.ejs**
  - The home page of the application.
  - Contains navigation links to other pages such as Login, Sign Up, and Search.
  - Features a hero section introducing the application.
  - Provides content about the application and its features.
- **signup.html**
  - Sign-up page for new users.
  - Includes a form for entering username, email, and password.
  - Validates password confirmation before submission.
- **login.html**
  - Login page for existing users.
  - Includes a form for entering email and password.
- **search.ejs**
  - Search page accessible after user login.
  - Displays a form to search for celebrities by name.
  - Shows search results with links to detailed profiles.
- **profile.ejs**
  - Profile page displaying detailed information about a selected celebrity.
  - Includes sections for biography, filmography, and social media links.

### Backend Files
- **server.js**
  - Main server file that initializes the Express application.
  - Sets up middleware for body parsing, static file serving, and session management.
  - Connects to Firebase using service account credentials.
  - Defines routes for the home page, login, signup, search, and profile.
  - Implements logic for user authentication and data retrieval.
  - Fetches celebrity details from the third-party API and processes them.

### Public Files
- Contains static assets such as CSS files and images used in the frontend.

## Routes and Endpoints
- **GET /**
  - Renders the home page (home.ejs).
- **POST /loginSubmit**
  - Handles user login.
  - Validates user credentials against Firebase Firestore.
  - Redirects to the search page upon successful login.
- **POST /signupSubmit**
  - Handles user sign-up.
  - Checks if the email already exists in the database.
  - Adds new user data to Firebase Firestore.
- **GET /search**
  - Renders the search page (search.ejs).
  - Requires user authentication.
- **POST /searchSubmit**
  - Fetches search results for celebrities based on user input.
  - Returns the search results in JSON format.
- **GET /profile/:id**
  - Renders the profile page for the specified celebrity (profile.ejs).
  - Fetches detailed information about the celebrity using the API.

## How to Run the Project
1. **Clone the repository**:
   ```sh
   git clone https://github.com/your-username/celebrity-details.git
   cd celebrity-details
   ```
2. **Install dependencies**:
   ```sh
   npm install
   ```
3. **Set up Firebase**:
   - Obtain Firebase service account credentials and save the file as `key.json` in the project root.
   - Ensure Firebase Firestore is set up for user data storage.
4. **Set up Environment Variables**:
   - Create a `.env` file to store sensitive information such as API keys.
5. **Start the server**:
   ```sh
   node server.js
   ```
6. **Access the application**:
   - Open your browser and navigate to `http://localhost:2000`.
