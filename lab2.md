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

      - When sending this message, several `methods` (such as `getPath()`, `getQuery()`, `indexOf()`, `concat()`, `substring()`, `replace()`) are called. These `methods'` `arguments` all pertain to the various `datatypes` that are present. Going down the list, `getPath()'s` `argument` takes in an `URI` argument in order to extract the `path` of a given `URL` as the `return value`. The `method`, `getQuery()` is similar to that of `getPath()` as it accepts an `URI` argument in to extract the `queries` (as the `return value`) present within the `URL`. As the code begins to parse through the `path` and `queries`, `indexOf()` takes a `character` as an `argument` and finds the position of that specific `character` in a `string` with an `integer` as a `return value`. The `concat()` takes a `string` as an argument and `concatenates` the `string` with the `object` calling the `method`, resulting a `concatenated string` as the `return value`. For `substring()`, it takes a `string` as an argument and finds it within the `object` calling the `method`. If the `string` is found, it returns an `integer` of the first-occuring pattern as a `return value`. Last but not least, `replace()` is a `method` that takes two `arguments` (the first one being the pattern to look for, and the second being the one to replace said pattern) and `returns` the corrected `string` as the value. All these `arguments` are contingent by the `request`; If you were to change any of the `path`/`query` values, the `return value` would indeed **change** as well. This is because the code retrieves data given from the `URL` that is being sent to the `webserver` and is responsible for changing any relevant fields of the class to the appropriate `values`.
      
- ## Part 2:
  - ...
 
- ## Part 3:
  - ...



