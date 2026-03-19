## Project Structure

- `index.html`: The main entry point of the website.
- `assets/`:
  - `css/`: Contains the styles for the website.
  - `js/`: Contains the JavaScript files.
  - `images/`: Contains all the images and assets used in the website.

## How to Host on GitHub Pages

1. Create a new repository on GitHub.
2. Upload all the files in this directory to the repository.
3. Go to the repository settings.
4. Navigate to the "Pages" section.
5. Select the branch (usually `main`) and the folder (usually `/root`) to serve from.
6. Click "Save". Your website will be live at `https://<your-username>.github.io/<repository-name>/`.

## Local Development

Simply open `index.html` in any modern web browser to view the website locally.

## Hosting with Node.js

1. Ensure you have [Node.js](https://nodejs.org/) installed.
2. Open your terminal in the project directory.
3. Install the dependencies:
   ```bash
   npm install
   ```
4. Start the server:
   ```bash
   npm start
   ```
5. Open your browser and navigate to `http://localhost:3000`.
6. To see a personalized invitation, use: `http://localhost:3000/?name=YourName`.

## Hosting on Netlify

1. **Manual Deploy**:
   - Log in to [Netlify](https://www.netlify.com/).
   - Drag and drop the project folder (or the extracted ZIP contents) into the Netlify "Sites" dashboard.
2. **GitHub Integration**:
   - Push this project to a GitHub repository.
   - Connect your GitHub repository to Netlify.
   - Netlify will automatically detect the `netlify.toml` and deploy your site.
3. **Personalized Links**: Once deployed, your links will look like `https://your-site-name.netlify.app/?name=GuestName`.
