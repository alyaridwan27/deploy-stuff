# Deploying Front end and Back end on Vercel
## Deploy Front End
1. Connect to Vercel:

> Go to Vercel and log in or sign up.
> Click on "New Project" and select "Import Git Repository".
> Choose your front end repository from GitHub.

2. Configure the Project:

> Vercel should auto-detect your front end framework (e.g., React, Next.js, etc.).
> Ensure the correct build settings are in place. For example, for a React app, the build command is typically npm run build and the output directory is build.

3. Environment Variables:

If your front end requires environment variables (e.g., API keys), set them up in the Vercel project settings under the "Environment Variables" section.

4. Deploy:

> Click "Deploy" to deploy your front end application.
> After deployment, you will get a live URL for your front end.

## Deploy Back End
1. Connect to Vercel:

> Go back to your Vercel dashboard.
> Click on "New Project" and select "Import Git Repository".
> Choose your back end repository from GitHub.

2. Configure the Project:

> Vercel will detect your back end framework (e.g., Node.js, Express).
> Set up the build and output settings. For a Node.js/Express app, ensure the entry point is correct (e.g., index.js or server.js).

3. Environment Variables:

Set up any required environment variables for your back end (e.g., database connection strings) in the Vercel project settings under "Environment Variables".

4. Database Connection:

If you are using a cloud-hosted MySQL database, configure the connection details as environment variables (e.g., MYSQL_HOST, MYSQL_USER, MYSQL_PASSWORD, MYSQL_DATABASE).

5. Deploy:

> Click "Deploy" to deploy your back end application.
> After deployment, you will get a live URL for your back end API.


## Connect BE and FE
1. Update API Endpoints in Front End:

> Update your front end code to point to the live URL of your deployed back end for API calls.
> You can use environment variables to manage this. For example, create a .env file with the back end URL:
```
REACT_APP_API_URL=https://your-backend-url.vercel.app
```
> In your front end code, use this variable to make API requests:
```
const apiUrl = process.env.REACT_APP_API_URL;
fetch(`${apiUrl}/api/endpoint`)
  .then(response => response.json())
  .then(data => console.log(data));
```

2. Environment Variables in Vercel:

Make sure these environment variables are also set in the Vercel project settings for the front end.
