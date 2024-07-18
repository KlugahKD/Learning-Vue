# Running the Vue Application Locally

This guide will walk you through the steps to run the Vue application and its accompanying server on your local machine.

## Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (Preferably the latest LTS version)
- npm (Comes installed with Node.js)

## Steps to Run the Application

1. **Clone the Repository**

   If you haven't already, clone the repository to your local machine. Use the following command in your terminal:
   ```bash
    git clone https://github.com/KlugahKD/Learning-Vue.git

2. **Navigate to the Project Directory**

  Change into the project directory (vue-learning) with:
   ``` cd vue-learning ```

3. **Install Dependencies**

Install the necessary npm packages by running:
```npm install```

4. **Start the Vue Application**

Launch the development server for the Vue application:
```npm run dev```

This command starts the Vue application on a development server. You should see output indicating the URL to access the application, typically `http://localhost:3000`.

5. **Run the Backend Server**

Open another terminal window or tab. Ensure you are still in the project directory, then start the backend server with:
```npm run server```


This command runs a local server that the Vue application will communicate with to fetch data. The server typically runs on `http://localhost:5000`.

## Accessing the Application

After both servers are running, open a web browser and navigate to `http://localhost:3000` to view the Vue application. The application should now be able to communicate with the backend server to fetch and display data.

## Troubleshooting

- If you encounter any issues with `npm install`, try clearing the npm cache with `npm cache clean --force` and then run `npm install` again.
- Ensure both the Vue application and the backend server are running on their respective ports without conflicts. If necessary, you can change the port for either process by modifying the respective configuration files.

Congratulations! You should now have the Vue application running locally on your machine.
