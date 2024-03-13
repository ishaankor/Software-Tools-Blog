# Lab Report 5 - Putting It All Together

- ## Part 1: Debugging Scenario
  - ### Student Post:
    - "When running `chat-server-pro`, I noticed that having a link that wants to both **chat** and             **save** creates a bug (or at the very least, wrong behavior). My guess for this bug occurring is         that the `else` conditional doesn't get reached because the first `if` already returns the                `chatHistory`. What can I do to fix this behavior?"
      ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/0ae43218-20a4-4a7e-8011-e413ffe26ab5)
  - ### TA Response:
    - "Hi, there! That's a great guess on what the bug might be! To help you out, what can you do to            implement this part of parsing the url? There are many ways to go about this -- try to first look         into the 'if' conditional and see how you can parse through other queries."
  - ### Screenshot/Terminal Output:
    - Given that the student took the TA's response into consideration, they would realize how the bug          has to do with how the program parses `/save` in this instance. Because `/save` is a **query** and        not part of the message string, the program fails to recognize it as a path (this explains why the        `else` conditional does not get run).
      - Screenshot:
        ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/eebe905e-ce74-4a9d-aaca-6bee5d23e772)
      - Terminal Readings:
        ```
        [user@sahara ~/chat-server-pro]$ bash run-chatserver.sh 4011
        Server Started! Visit http://localhost:4011 to visit.
        Message string: [message]/save?name
        /save FOUND in Message string!
        Now parsing '/save' as a query...
        Filename string: [filename]
        ```
  - ### Required Information:
    - File & directory structure:
      - In this directory structure, the two files that are involved are `ChatServer.java` and
        `run-chatserver.sh`. The bash file (`chatserver.sh`) is what compiles and runs the ChatServer             with a dedicated server port number if provided. The Java file (`ChatServer.java`) is what runs           the chat server and allows the users to save the chat history and retrieve at a later time.

        <img src="https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/25ac5028-112d-4777-b347-f276d2c66ee8" alt="drawing" width="200"/>
    - Contents of file before the fix:
      - `ChatServer.java`:
        ```
        if (url.getPath().equals("/chat")) {
          String[] params = url.getQuery().split("&");
          String[] shouldBeUser = params[0].split("=");
          String[] shouldBeMessage = params[1].split("=");
          if (shouldBeUser[0].equals("user") && shouldBeMessage[0].equals("message")) {
            String user = shouldBeUser[1];
            String message = shouldBeMessage[1];
            this.chatHistory += user + ": " + message + "\n\n";
            return this.chatHistory;
        } else {
          return "Invalid parameters: " + String.join("&", params); }
        }
        ```
    - URL ran to trigger the bug:
      - `http://localhost:4011/chat?user=[name]&message=[message]/save?name=[filename]`
    - Bug fix description:
      - In order to fix this *weird behavior*, it is important to make the program understand that                `/save` is a query and not part of the message string. To do that, I first searched for the query         by using `contain("/save")` on the message string and then splice the string to only capture              everything before the '/'. After that, the program then finds the filename by parsing through the         `params` variable. With this modification, the program sends the message and then saves the               entire chat history at the same time.
        ```
        if (url.getPath().equals("/chat")) {
          String[] params = url.getQuery().split("&");
          String[] shouldBeUser = params[0].split("=");
          String[] shouldBeMessage = params[1].split("=");
          if (shouldBeUser[0].equals("user") && shouldBeMessage[0].equals("message")) {
            String user = shouldBeUser[1];
            System.out.println("Message string: " + shouldBeMessage[1]);
            if (shouldBeMessage[1].contains("/save")) {
              System.out.println("/save FOUND in Message string!");
              System.out.println("Now parsing '/save' as a query...");
              String message = shouldBeMessage[1].substring(0, shouldBeMessage[1].indexOf("/"));
              this.chatHistory += user + ": " + message + "\n";
              String shouldBeFileName = params[1].split("=")[2];
              System.out.println("Filename string: " + shouldBeFileName);
              File directory = new File("chathistory");
              File file = new File(directory, shouldBeFileName);

              try (BufferedWriter writer = new BufferedWriter(new FileWriter(file))) {
                writer.write(this.chatHistory);
                return "Data written to " + shouldBeFileName + "in 'chat-history' folder.";
              } catch (IOException e) {
                e.printStackTrace();
                return "Error: Something wrong happen during file save, check StackTrace";
              }
            }
            else {
              String message = shouldBeMessage[1];
              this.chatHistory += user + ": " + message + "\n";
            }
            return this.chatHistory;
          } else {
            return "Invalid parameters: " + String.join("&", params);
          }
        }
        ```
- ## Part 2: Reflection
  - In this second half of the quarter, it was interesting to learn about `jdb` as another type of debugging. Learning `JUnit` tests was definitely fun to learn about as it was my first step into the world of Java debugging. The `jdb` concept was very eye-opening in the sense that it enables me to view the specific processes that a program has running and view its properties. It makes me feel as though that I can pause time and be able to be a part of the threads and subprocesses. With abilities of making breakthroughs and identifying the value of every variable, it makes the debugging process much easier for me. I always loved the idea of seeing the changes in variables mid-program as it shows if the process is working as intended!
