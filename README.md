# Simple Concurrent WebServer

## Overview
This is a multithreaded web server application written in Java. It serves HTML files and Base64-encoded image files, capable of handling multiple client connections concurrently. The server limits the number of concurrent clients and provides a custom response when this limit is exceeded.

## Usage
- **GET Request**: The server responds to GET requests by serving the requested file.
- **POST Request**: The server accepts POST requests to `/data` and saves the request body to a text file on the server.
- **Client Limit**: The server limits the number of concurrent clients to 10. When this limit is exceeded, the server responds with a custom message.
- **File Types**: The server serves HTML, CSS, JavaScript, PNG, JPG, and JPEG files directly from the local disk. Image files are Base64-encoded before being embedded in the HTML response.
- **Error Handling**: The server responds with a `404 Not Found` error when a requested file is not found.
- **Logging**: The server logs each request to the console.
- **Concurrency**: The server uses a thread pool to manage multiple client connections concurrently.
- **Graceful Shutdown**: The server can be gracefully shut down by sending a `SIGINT` signal (Ctrl+C).

---------- 

## How to Run
1. **Clone the repository**:
   ```bash
   git clone https://github.com/Hajaku12/Lab1_webserver.git
   cd Lab1_webserver
   ```

2. **Compile and Run the Server**:
   ```bash
   mvn package
   java -cp target/arep_lab1-1.0-SNAPSHOT.jar org.example.SimpleWebServer

   ```

3. **Access the Web Server**:
    - Open a web browser and navigate to `http://localhost:8080`.
    - The server will serve files from the `src/main/resources` directory.

## Dependencies
- **Maven**: The project uses Maven to manage dependencies and build the project.
- **JUnit 4**: The project uses JUnit 4 for unit testing.

## Configuration
- **Root Directory**: The server serves files from the `src/main/resources` to access each type of file it is necessary to enter the corresponding path depending on the type of file.
- **Port**: The server operates on port `8080` by default.
- **Thread Pool**: The pool size is 10 by default, but it can be modified in the `SimpleWebServer` class.

---------

## Implementation
![html.png](images%2Fhtml.png)
![index.png](images%2Findex.png)
![jpg.png](images%2Fjpg.png)
![js.png](images%2Fjs.png)
![png.png](images%2Fpng.png)
![txt.png](images%2Ftxt.png)
----------

## Generating Project Documentation

1. **Generate the Site**
    - Run the following command to generate the site documentation:
      ```sh
      mvn site
      ```

2. **Add Javadoc Plugin for Documentation**
    - Add the Javadoc plugin to the `reporting` section of the `pom.xml`:
      ```xml
      <project>
        ...
        <reporting>
          <plugins>
            <plugin>
              <groupId>org.apache.maven.plugins</groupId>
              <artifactId>maven-javadoc-plugin</artifactId>
              <version>2.10.1</version>
              <configuration>
                ...
              </configuration>
            </plugin>
          </plugins>
        </reporting>
        ...
      </project>
      ```

    - To generate Javadoc as an independent element, add the plugin in the `build` section of the `pom.xml`:
      ```xml
      <project>
        ...
        <build>
          <plugins>
            <plugin>
              <groupId>org.apache.maven.plugins</groupId>
              <artifactId>maven-javadoc-plugin</artifactId>
              <version>2.10.1</version>
              <configuration>
                ...
              </configuration>
            </plugin>
          </plugins>
        </build>
        ...
      </project>
      ```

3. **Generate Javadoc Commands**
    - Use the following commands to generate Javadocs:
      ```sh
      mvn javadoc:javadoc
      mvn javadoc:jar
      mvn javadoc:aggregate
      mvn javadoc:aggregate-jar
      mvn javadoc:test-javadoc
      mvn javadoc:test-jar
      mvn javadoc:test-aggregate
      mvn javadoc:test-aggregate-jar
      ```

---------

## Setting Up Git

### Install Git
- Follow the instructions on the Git website: [Git Installation Guide](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### Verify Git Installation
- Run the following command to verify Git is installed:
  ```sh
  git --version
  ```
- The output should look similar to:
  ```sh
  git version 2.2.1
  ```

### Configure Git Identity and Default Editor
- Set your name and email:
  ```sh
  git config --global user.name "John Doe"
  git config --global user.email johndoe@example.com
  git config --global core.editor emacs
  ```

- Review your configuration:
  ```sh
  git config --list
  ```
- You should see output similar to:
  ```sh
  user.name=Daniel Benavides
  user.email=dnielben@gmail.com
  core.editor=emacs
  ```

### Create a Git Repository
- In your project directory, initialize a Git repository:
  ```sh
  git init
  ```

### Commit Changes to Git
- To create a new version and commit the changes, run:
  ```sh
  git commit -m 'Primera versión del proyecto'
  ```

### List Remote Repositories
- To list remote repositories you have worked with, run:
  ```sh
  git remote
  ```

### Push Changes to Remote Repository
- Push the latest version of your project to the remote repository:
  ```sh
  git push -u origin master
  ```

### Add More Files to Your Git Project and Remote Repository
- It is recommended to create a README, LICENSE, and .gitignore file:
  ```sh
  echo 'Mi primer proyecto' > README.txt
  echo 'TODO: Copiar el texto de la licencia http://www.gnu.org/licenses/gpl.html' > LICENSE.txt
  echo '# TODO: Copiar los contenidos de https://github.com/github/gitignore/blob/master/Java.gitignore' > .gitignore
  ```

- Add the files to the repository:
  ```sh
  git add *.txt
  git add .gitignore
  ```
---------

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE.txt) file for details.

----------
## Author
Hann Jang
