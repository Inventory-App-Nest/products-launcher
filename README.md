## Dev

1. Clone the repository  
2. Create a `.env` file based on `.env.template`  
3. Run the command:  
   ```sh
   docker compose up --build
   ```

### Steps to Create Git Submodules

1. Create a new repository on GitHub  
2. Clone the repository to your local machine  
3. Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want to store the submodule (it must not exist in the project)  
   ```sh
   git submodule add <repository_url> <directory_name>
   ```
4. Add the changes to the repository (`git add`, `git commit`, `git push`)  
   Example:  
   ```sh
   git add .
   git commit -m "Add submodule"
   git push
   ```
5. Initialize and update submodules. When someone clones the repository for the first time, they must run the following command to initialize and update the submodules:  
   ```sh
   git submodule update --init --recursive
   ```
6. To update submodule references:  
   ```sh
   git submodule update --remote
   ```

## Important
When working with a repository that contains submodules, **first update and push** the submodule and **then** push to the main repository.  

If done in reverse order, submodule references in the main repository will be lost, leading to potential conflicts that must be resolved.