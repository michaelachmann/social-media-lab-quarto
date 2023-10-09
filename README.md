# Social Media Lab Quarto

Welcome to the Social Media Lab Quarto, a growing compilation of notes centered around social media analysis, with a spotlight on computational methodologies. This project, both a website and an informational resource, is woven into the fabric of my PhD project and teaching endeavors at the Media Informatics Group, University of Regensburg, Germany.

## Getting Started with Collaboration

### Prerequisites

#### Install Quarto

Before you can effectively collaborate on this project, it's essential to install Quarto. Quarto is an open-source scientific and technical publishing system built on Pandoc. Follow the steps below for installation:

- Navigate to [Quarto's download page](https://quarto.org/docs/getting-started/installation.html).
- Choose the appropriate installer for your operating system (Windows, macOS, Linux) and follow the installation instructions.
- Verify the installation by opening your terminal (or command prompt) and running: `quarto --version` This should display the installed Quarto version.

### Clone the Repository

After ensuring Quarto is installed, proceed to clone the repository to get a local copy on your machine.

1. **Access the Repository**
 - Ensure you've received access to the GitHub repository "social-media-lab-quarto".
 
2. **Clone the Repository**
 - Open your terminal or command prompt.
 - Navigate to the directory where you wish to clone the repository using `cd` command.
 - Run the following Git command to clone the repository:
   ```
   git clone git@github.com:michaelachmann/social-media-lab-quarto.git
   ```

### Collaborate on the Project

After successfully cloning the repository, you can begin collaborating on the project.

1. **Create a New Branch**
 - Always create a new branch for your work: 
   ```
   git checkout -b [branch-name]
   ```
   Replace `[branch-name]` with a descriptive name for your branch (e.g., `update-analysis-notes`).

2. **Make Changes**
 - Modify, add, or remove files as needed, ensuring to follow any coding and documentation standards.

3. **Commit Your Changes**
 - Add your changes to the staging area:
   ```
   git add .
   ```
 - Commit your changes:
   ```
   git commit -m "Descriptive message about your changes"
   ```
 
4. **Push to GitHub**
 - Push your branch to GitHub:
   ```
   git push origin [branch-name]
   ```

5. **Open a Pull Request**
 - Go to the GitHub repository and navigate to "Pull requests".
 - Click "New pull request" and choose your branch.
 - Add relevant comments and request reviews if necessary.
 - Click "Create pull request".

### Working with Quarto

As the project heavily relies on Quarto, ensure to regularly utilize its capabilities in knitting documents, creating slides, or building books/website components. More details on working with Quarto can be found in [Quarto’s documentation](https://quarto.org/docs/intro.html).

## Running and Publishing the Website

### Preview Website Locally

To visualize changes you make to the website before pushing them to the live server, use Quarto’s local preview feature:

1. **Navigate to the Website Directory**
   - Ensure you are in the root directory of the project where the Quarto configuration file (`_quarto.yml`) is located.
   
2. **Run Local Preview**
   - In your terminal or command prompt, run the following command:
     ```
     quarto preview
     ```
   - This will build and serve your website locally. You should be able to view it by navigating to the URL provided in the terminal, typically `http://127.0.0.1:4321`.

3. **View and Validate**
   - Explore the website in your local web browser and validate that your changes are rendered as expected.
   
Ensure that all navigational links, images, and content appear as intended and that you thoroughly validate your changes before publishing them live.

### Publish Website to GitHub Pages

Once you are satisfied with your changes and have committed them to your branch, you can publish the website to GitHub Pages.

1. **Publish with Quarto**
   - Use Quarto to publish the website to GitHub Pages by running:
     ```
     quarto publish gh-pages
     ```
     If you're using a custom domain or path, you might need to provide additional arguments. Refer to the [Quarto documentation](https://quarto.org/docs/publishing/github-pages.htmls) for more details.

2. **Verify Live Website**
   - An administrator will have to approve your publish request.
   - Once published, visit [the website](https://social-media-lab.net/) and confirm that all changes are reflected accurately.




## Contact

For any inquiries or further information, feel free to reach out to [Michael Achmann](mailto:michael.achmann@informatik.uni-regensburg.de).
