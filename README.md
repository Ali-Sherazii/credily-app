# Credily App!

This project is structured into separate frontend and backend directories.

## Project Structure

- `frontend/` - React frontend built with Vite
- `backend/` - Node.js backend

## Setup Instructions

### Root Directory Setup

1. First, install dependencies in the root directory:
   ```
   npm install
   ```
   This will set up the necessary packages for the project root.

### Frontend Setup

1. Navigate to the frontend directory and install dependencies:
   ```
   cd frontend
   npm install
   ```
2. Create a `.env` file with your API port:
   ```
   VITE_API_PORT=5000  # or 4000 based on your preference
   ```
3. Start the development server:
   ```
   npm run dev
   ```

### Backend Setup

1. Navigate to the backend directory and install dependencies:
   ```
   cd backend
   npm install
   ```
2. Create a `.env` file with:

   ```
   PORT=5000  # or 4000 based on your preference
   MONGODB_URI=your_connection_string_from_table_below
   JWT_SECRET=your_jwt_secret
   NODE_ENV=development

   # Cloudinary credentials (required for image uploads)
   # Create an account at cloudinary.com and get these from your dashboard
   CLOUDINARY_CLOUD_NAME=ds6xri71k
   CLOUDINARY_API_KEY=632696559246236
   CLOUDINARY_API_SECRET=PaT4mWgag51BgW_dpK835_W8Fhc   # Google Cloud credentials for sentiment analysis
   GOOGLE_APPLICATION_CREDENTIALS=./config/google-credentials.json
   USE_REAL_SENTIMENT=true
   ```

   > **Note:** The Cloudinary variables are essential for profile picture uploads and other media storage features. Create a free account at [cloudinary.com](https://cloudinary.com) to get your credentials.

3. **Google Cloud Setup:** You need to add the `google-credentials.json` file in the `backend/config` directory. This file contains the credentials for Google Cloud services used for sentiment analysis.

   If you don't add this file, sentiment analysis features will not work correctly.

4. Start the backend server:
   ```
   npm run dev
   ```
5. To test your database connection:
   ```
   node test-db-connection.js
   ```

## Deployment

The backend is deployed on the render and the frontend is deployed on the vercel.
You can explore the web application via link below using the demo credential (username: demo-account password: 123456) or simply signup.
https://credily-app-blond.vercel.app/login


Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
