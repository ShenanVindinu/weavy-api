# Weavy API Demo 🥬💖🧦🏆

This project is a simple React application that integrates with the [Weavy API](https://www.weavy.com/) to manage users. It currently supports creating a user via the Weavy Web API, with plans to expand to listing, updating, and deleting users.

## Features
- **Create User**: Add a new user to the Weavy environment using the `POST /api/users` endpoint.
- Environment variables for secure configuration (API URL and key stored in `.env`).

## Prerequisites
- [Node.js](https://nodejs.org/) (v14 or later recommended)
- A Weavy account and environment (sign up at [weavy.com](https://www.weavy.com/))
- A Weavy API key and environment URL

## Setup

### 1. Clone the Repository
```bash
git clone https://github.com/ShenanVindinu/weavy-api.git
cd weavy-demo
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory and add your Weavy environment details:
```
REACT_APP_WEAVY_URL=https://your-environment.weavy.io
REACT_APP_API_KEY=your-api-key
```
- Replace `https://your-environment.weavy.io` with your Weavy environment URL.
- Replace `your-api-key` with your Weavy API key.

### 4. Run the App
```bash
npm start
```
The app will start at `http://localhost:3000`.

## Usage
1. Open the app in your browser.
2. Fill out the "Create User" form with:
   - **UID**: A unique identifier for the user (e.g., `testuser1`).
   - **Name**: The user’s name (e.g., `Test User`).
   - **Email**: The user’s email (e.g., `test@example.com`).
3. Click "Create" to send the request to the Weavy API.
4. Check the browser console for detailed logs (URL, payload, response, or errors).

## API Integration
The app uses the Weavy Web API’s `POST /api/users` endpoint to create users. Example request:
```bash
curl -X POST "https://8015b5dbc0724d38882ac90397c27649.weavy.io/api/users" \
-H "Authorization: Bearer wys_hMWpXdekxcn9Gc8Ioah3azOllzUZ7l3HN9yB" \
-H "Content-Type: application/json" \
-d '{"uid": "testuser1", "name": "Test User", "email": "test@example.com"}' \
--ssl-no-revoke
```

### Current Implementation
- **Frontend**: React with `axios` for API calls.
- **Endpoint**: `POST /api/users` to create a user.
- **Error Handling**: Logs errors to the console and shows alerts for success/failure.

## Troubleshooting
- **404 Error**: Ensure the `REACT_APP_WEAVY_URL` matches your Weavy environment URL.
- **SSL Issues**: If running locally on Windows, use `--ssl-no-revoke` with `curl` for testing. Browser SSL issues may require Weavy support.

## License
This project is licensed under the MIT License.

---
