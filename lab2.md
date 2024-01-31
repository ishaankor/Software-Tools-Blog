# Lab Report 2 - Servers and SSH Keys

- ## Part 1:
  - My `ChatServer` code block:
    
     ![Imgur](https://imgur.com/ieWxHW0.png)
    
  - The `add-message` command:

    - First message with '*jpolitz*' and "**Hello**"

      ![Imgur](https://i.imgur.com/8nNhz5w.jpeg)
 
      returns...

      ![Imgur](https://i.imgur.com/a8LHfGz.jpeg)
 

    - Second message with '*yash*' and "**How are you**"
   
      ![Imgur](https://i.imgur.com/eUUpHeF.jpeg)

      returns...

      ![Imgur](https://i.imgur.com/bXYPvC7.jpeg)

      - When sending this message, several `methods` (such as `getPath()`, `getQuery()`, `indexOf()`, `concat()`, `substring()`, `replace()`) are called. These `methods'` `arguments` all pertain to the various `datatypes` that are present. Going down the list, `getPath()`'s `argument` takes in an `URI` argument in order to extract the `path` of a given `URL` as the `return value`. The `method`, `getQuery()` is similar to that of `getPath()` as it accepts an `URI` argument in to extract the `queries` (as the `return value`) present within the `URL`. As the code begins to parse through the `path` and `queries`, `indexOf()` takes a `character` as an `argument` and finds the position of that specific `character` in a `string` with an `integer` as a `return value`. The `concat()` takes a `string` as an argument and `concatenates` the `string` with the `object` calling the `method`, resulting a `concatenated string` as the `return value`. For `substring()`, it takes a `string` as an argument and finds it within the `object` calling the `method`. If the `string` is found, it returns an `integer` of the first-occuring pattern as a `return value`. Last but not least, `replace()` is a `method` that takes two `arguments` (the first one being the pattern to look for, and the second being the one to replace said pattern) and `returns` the corrected `string` as the value. All these `values` are contingent by the `request`; If you were to change any of the `path`/`query` values, the `return value` would indeed **change** as well. This is because the code retrieves data given from the `URL` that is being sent to the `webserver` and is responsible for changing any relevant fields of the class to the appropriate `arguments`. In the event that a duplicate message is being sent, `values` (such as the `path` and `query` will not change but the `return value` does as the `message` continues to be `concatenated` onto the `string` that "records" the chat messages (`chat_room`). 
      
- ## Part 2:
  
  - Absolute path to the *private* key for my SSH key for logging into `ieng6`
 
    ![Imgur](https://i.imgur.com/Jw5cMPg.jpeg)

    - This credential (**id_rsa**) is what allows me to *privately* access the `ieng6` machines in the CSE Lab. Being a *private* authentication, it allows me to remotely connect to a system through the identification of my local host (computer) rather than a general one (*public* key). 
 
  - Absolute path to the *public* key for my SSH key for logging into `ieng6`
 
    ![Imgur](https://i.imgur.com/Jw5cMPg.jpeg)

    - This credential (**id_rsa.pub**) is what allows me to *publicly* access the `ieng6` machines in the CSE Lab. Because it is a *public* token of access, I am connecting to a specific `ieng6` machine through a public connection. This means that I am connecting through a general gateway rather a gated one (*private* key). 

 
  - Terminal interaction where logging into my `ieng6` account *without* being asked for a password
 
    ![Imgur](https://i.imgur.com/bOv5RWa.jpeg)

    - The terminal shows how I am able to log into my `ieng6` account given that I provided the right authorization tokens (*private/public* keys). Because these keys are stored within the computers, I am able to log into the `ieng6` machine without the need of providing my password for every instance. 

 
- ## Part 3:
  
  - For starters, I did not know about the `man` and `scp` commands. I think learning this from lab 3 taught me a great amount of how to properly navigate through `Linux` and the `terminal`. The `man` command is a fantastic find for learning a particular `commands` abilities and modes - this will be great in also explaining how a command is best used. On the other hand, `scp` taught me more about the functionality of `remote connections/session`. Being able to *securely copy files* from one environment to another is an amazing tool to have behind my belt, if I do say so myself!  



