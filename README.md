# Insights Fullstack homework

Hello, this is a homework asignment to get to test out your Javascript, HTML and CSS abilities.
The currently provided HTML is working, but isn't display the data like we want it to.

**Intro**

The website gets a list of phones from a certain API and displays it in a table.
Each row has also a button that when clicked on, displays the ID of the phone in a seperate element.

 The homework consists of a few tasks:
 1. Fix the data recieved - besides the name, all of the fields are showing `undefined`. In the given columns fill out as much information as you can with the given data. **NOTE: not all fields contain data**
 2. Fix the "Get Id" functionality - when you press on the button the ID of the phone should be displayed, but currently it shows only one value.
 3. Color the cell of the price, for any price above 500.
 4. Color all odd table rows in `gray` and even table rows in `darkgrey` (or any other color you like)
 5. Centrelize the table
 6. Reduce the size of the Selected Phone Id field and the header

**You can keep track of your progress by looking at the final result screenshot**

After completing the task, you should create send the code files with the solution in a ZIP to the email that you recieved the task in.

Final Result Screenshot:
<img width="1512" alt="Screenshot 2024-07-01 at 15 29 58" src="https://github.com/NikitaAiz/insights_fullstack/assets/73474213/92969c49-4172-474f-bcc9-fac74be7a8eb">

# Shachar's explanations
In this section, I will clarify the decisions I made during the code-writing process.

**index.html**

* I have utilized the name field of certain objects to extract additional information. For instance, the phone's generation is written in the name field of some objects. I have created helper functions to extract the generation, capacity, and color of the phone if this information is present in the name field.
  
* I opted not to use the "Strap Colour" field in the Apple Watch Series 8 object because it specifies the color of the watch strap rather than the watch itself.

* For the Apple Watch Series 8 and similar products like the Google Pixel 6 Pro, I was unsure if "8" and "6" represented the generation, so I did not include it in the Generation column.
   
* I used the "Hard disk size" field from the Apple MacBook Pro 16 object to fill in the "Capacity" column in the phone table.
   
* I made a fix to the "Get Id" functionality by changing "var index = 0" in the for loop to "let index = 0". The scope of 'var' is function-based and not block-based. This means that the index variable will be shared between all the loop runs. It's better to use let so that the value will always be correct. Using let will ensure that the value of the index variable will always be re-initialized, unlike when using var, which gets stuck on the same value after running the loop for the first time.
   
* In the attachButtonEvents function, the code was used to capture all button elements across the entire document, instead of just the "Get ID" buttons in the phone table. Clicking any button across the document updated the result with the final index. I've modified the function so that only when the user clicks each "Get ID" button in the table, the corresponding phone ID correctly displays in the result. You can uncomment the hello button to see the change.
  
* Placing scripts at the end allows the HTML content to load first. 
  
**Tests**

* I created a test suite using jest to validate the functionality of the extractCapacityFromName, extractGenerationFromName, and extractColorFromName functions in nameManipulation.js. I ran it with the "npm test" command after installing jest with "npm install --save-dev jest". Node.js should be installed in order to run the tests.

Example: <br>
<img width="400" alt="Tests" src="https://github.com/ShacharAdam/BGUDrugChallenge2023/blob/main/TestSuite.png?raw=true">


**Responsive Design**

* I have implemented a responsive design using media queries to ensure that the content is displayed optimally across different devices and screen sizes. However, the design has not been adapted to all screen sizes, but I aimed to illustrate the importance of doing so.


Shachar's Final Result Screenshot:
<img width="1512" alt="Shachar solution" src="https://github.com/ShacharAdam/BGUDrugChallenge2023/blob/main/ShacharSolution.png?raw=true">



