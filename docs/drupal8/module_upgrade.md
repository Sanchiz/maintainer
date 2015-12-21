How to start upgrading Drupal 7 modules to Drupal 8
======

# Drupal 7 module has no 8.* branch.
1. Clone latest 7.x version from drupal.org:

    ```
    git clone --branch 7.x-1.x USERNAME@git.drupal.org:project/PROJECT_NAME.git
    ```
  
2. Create new branch 8.x-1.x based on latest Drupal 7 code:

    ```
    cd PROJECT_NAME
    git checkout -b 8.x-1.x
    ```
    
3. Move Drupal 7 code into `drupal7` folder and commit changes:

    ```
    mkdir drupal7
    git mv $(ls * | grep -vi "drupal7") drupal7
    ```
    
4. Create GitHub repository and push code to GitHub
5. Clone Vagrant Box for maintainers https://github.com/drupal-ukraine/maintainer to some place:

    ```
    git clone git@github.com:drupal-ukraine/maintainer.git
    cd maintainer
    cp -r maintainer/* ./
    cp -r maintainer/.gitignore ./
    ```
6. Create module folder in Drupal 8 code and move Drupal 7 code:

    ```
    mkdir d8/modules/PROJECT_NAME
    mv drupal7 d8/modules/PROJECT_NAME
    ```
    
7. Commit and push to GitHub