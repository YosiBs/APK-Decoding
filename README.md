<h1>APK Decoding and Bug Fixing Journey</h1>
    <p>This project involved decoding an APK file, analyzing its source code, fixing bugs, and completing a game to display the final <strong>FinishGame</strong> Toast message.</p>
   <h2>Steps to Solve the Bugs and Complete the Game</h2>
    <ol>
        <li>
            <strong>Decompiled the APK:</strong>
            <ul>
                <li>Used <a href="http://www.javadecompilers.com/apk" target="_blank">http://www.javadecompilers.com/apk</a> to decode the APK file.</li>
                <li>Extracted the <code>/sources</code> and <code>/resources</code> folders.</li>
                <li>Created a new Android Studio project and copied the Activities, layouts, and other required files.</li>
            </ul>
        </li>
        <li>
            <strong>Modified the AndroidManifest.xml:</strong>
            <ul>
                <li>Added the necessary permissions, such as <code>&lt;uses-permission android:name="android.permission.INTERNET" /&gt;</code>, to ensure proper functionality.</li>
            </ul>
        </li>
        <li>
            <strong>Identified and Fixed Bugs:</strong>
            <ul>
                <li>Encountered a <code>NullPointerException</code> due to missing or incorrect views in the layout file.</li>
                <li>Resolved an <code>ArrayIndexOutOfBoundsException</code> caused by accessing invalid indices in the sequence validation logic.</li>
                <li>Debugged and ensured the <code>arrowClicked()</code> and <code>finishGame()</code> methods worked as expected.</li>
            </ul>
        </li>
        <li>
            <strong>Played the Game to Find the Sequence:</strong>
            <ul>
                <li>The game's goal was to input the correct sequence using the arrow buttons (up, down, left, right).</li>
                <li>The sequence was derived by taking my <strong>ID</strong> and applying <code>mod 4</code> to each digit to generate a sequence of numbers (0, 1, 2, 3).</li>
            </ul>
        </li>
        <li>
            <strong>Completed the Game:</strong>
            <ul>
                <li>Input the correct sequence and fixed bugs until the game displayed the <strong>FinishGame</strong> Toast message.</li>
                <li>The final message was: <em>"Survived in &lt;state&gt;"</em> (screenshot attached below).</li>
            </ul>
        </li>
    </ol>

  <h2>How to Pass the Game</h2>
    <p>To pass the game, you need to determine the correct sequence of moves based on your ID. For example, using the ID <code>123456789</code>:</p>
    <ol>
        <li>Take each digit in the ID and calculate <code>digit % 4</code> to get the sequence:</li>
        <ul>
            <li>1 % 4 = 1 → <strong>Right</strong></li>
            <li>2 % 4 = 2 → <strong>Up</strong></li>
            <li>3 % 4 = 3 → <strong>Left</strong></li>
            <li>4 % 4 = 0 → <strong>Down</strong></li>
            <li>5 % 4 = 1 → <strong>Right</strong></li>
            <li>6 % 4 = 2 → <strong>Up</strong></li>
            <li>7 % 4 = 3 → <strong>Left</strong></li>
            <li>8 % 4 = 0 → <strong>Down</strong></li>
            <li>9 % 4 = 1 → <strong>Right</strong></li>
        </ul>
        <li>The final sequence for the ID <code>123456789</code> is:</li>
        <ul>
            <li><strong>Right, Up, Left, Down, Right, Up, Left, Down, Right</strong></li>
        </ul>
        <li>Use the arrow buttons to input this sequence into the game to pass!</li>
    </ol>

    
### Identify and Fix Bugs:
#### `Activity_Game.java`
1. **Update Toast Messages:**

   Change:
   ```java
     Toast.makeText(this, "Survived in " + state, 1).show();
     } else {
     Toast.makeText(this, "You Failed ", 1).show();
   ```
     
   To:
    ```java
    Toast.makeText(this, "Survived in " + state, Toast.LENGTH_LONG).show();
    } else {
    Toast.makeText(this, "You Failed ", Toast.LENGTH_LONG).show();
   ```

2. **Fix URL**
     Change:‌‌‌
    ```xml 
      <string name="url">https://pastebin.com/raw/‌‌‌‌‌‌‌‌‌‌‌‌‌‌‌ZWNJZWNJZWNJT67TVJG9</string>
    ```

    To:
    ```xml
        <string name="url">https://pastebin.com/raw/T67TVJG9</string>
     ```



    <h2>Final Toast Message Screenshot</h2>

    <p>A screenshot of the <strong>FinishGame</strong> Toast message:</p>
    <img src="https://github.com/user-attachments/assets/3afe0a38-7b8c-4400-8ecc-1686776944da" alt="FinishGame Toast Screenshot" width=250 >

### Video Demonstration:
Here is a video demonstration of the game:


  https://github.com/user-attachments/assets/dd7a4934-4741-4ea9-82bd-1c9a88565937

  <h2>Conclusion</h2>
  <p>This project was a comprehensive exercise in APK decoding, Android development, and debugging. It tested my ability to decompile and understand existing code, modify and fix bugs, and successfully interact with the app's logic to complete the challenge.</p>
