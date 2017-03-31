### Basic commands
  
  * **Init**: create a new repository
  
  ```
  git init
  ```
  
  * **Clone**: clone a repository
  
    * Clone a repository in local:
   
    ```
    git clone /path/to/repository/
    ```

    * Clone a repository in server:

    ```
    git clone username@serveraddress:/path/to/repository
    ```

  * **Branch**: 

    * Check the current branch:

    ```
    git branch
    ```

    * Create a new branch:

    ```
    git branch <name_branch>
    ```

  * **Check out**:

    * Check out an existing branch:
    
    ```
    git checkout <name_branch>
    ```

    * Create a new branch and check it out:

    ```
    git checkout -b <name_branch>
    ```
  
    * Return to master branch:

    ```
    git checkout master
    ```

  * **Add**: update a state (add, edit, delete) of files

    * Update all:

    ```
    git add .

    ```

    * Update files with a format

    ```
    git add *.<suffix>
    ```

    * Update files with their names

    ```
    git add <name_file_1> [<name_file_2> ... <name_file_n>] 
    ```

  * **Commit**: Confirm and save the modifing of the project

    ```
    git commit -am '<note>'
    ```

  * **Push**: Update the modifing of project on server

    * The branch exists

    ```
    git push origin <name_branch>
    ``` 
    
    * The branch doesn't exist

    ```
    git remote add origin <server>
    git push origin <name_branch>
    ```

* **Fetch**: Get the latest code on server and overwrite the source on local

  ```
  git fetch <name_branch>
  ```

* **Pull**: Get the latest code on server and merge with the code on local

  ```
  git pull <name_branch>
  ```
