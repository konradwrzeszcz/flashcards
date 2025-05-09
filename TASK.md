# Flashcard Application

A simple web application to display flashcards. Users can select a topic, view a card's front (question/term), and then reveal the card's back (answer/definition). The application will consist of an `index.html` file for the UI and a JavaScript file for the flashcard data.

## Task status

- [ done ] Task 1: Create HTML structure for the flashcard app (`index.html`)
  - [ done ] Task 1.1: Design basic layout (topic display, card display, buttons)
  - [ done ] Task 1.2: Implement elements for topic selection
  - [ done ] Task 1.3: Implement elements for card front (left side)
  - [ done ] Task 1.4: Implement elements for card back (right side - initially hidden)
  - [ done ] Task 1.5: Implement navigation/action buttons (e.g., "Next Card", "Flip Card")
- [ done ] Task 2: Create JavaScript file for flashcard data (`dictionary.js`)
  - [ done ] Task 2.1: Define the data structure: `map[topic] -> map[leftcardside] -> rightcardside`
  - [ done ] Task 2.2: Populate with initial sample data for at least one topic
- [ done ] Task 3: Implement core flashcard logic
  - [ done ] Task 3.1: Load flashcard data from `dictionary.js` into `index.html`
  - [ done ] Task 3.2: Implement topic selection functionality
  - [ done ] Task 3.3: Implement displaying the current card (left side)
  - [ done ] Task 3.4: Implement "Flip Card" functionality to show the right side
  - [ done ] Task 3.5: Implement "Next Card" functionality
- [ done ] Task 4: Style the application
  - [ done ] Task 4.1: Basic styling for readability and usability in `index.html` or a separate `style.css`
- [ done ] Task 5: Initialize `TASK.md` file (This task)
  - [ done ] Task 5.1: Initialize `TASK.md` with the feature name and description
  - [ done ] Task 5.2: Populate "Task status" section
  - [ done ] Task 5.3: Populate "Implementation plan" section
  - [ done ] Task 5.4: Populate "All relevant files" section
- [ done ] Task 6: Implement random card picking
  - [ done ] Task 6.1: Add a shuffle function for arrays
  - [ done ] Task 6.2: Modify `loadCardsForTopic` to shuffle cards when a topic is loaded
- [ done ] Task 7: Add more examples to existing topics
  - [ done ] Task 7.1: Add new question/answer pairs to "Sample Topic 1"
  - [ done ] Task 7.2: Add new question/answer pairs to "Sample Topic 2"
- [ done ] Task 8: Refactor navigation and random card selection
  - [ done ] Task 8.1: Remove "Previous Card" and "Next Card" buttons from HTML
  - [ done ] Task 8.2: Add a single "Next" button to HTML
  - [ done ] Task 8.3: Modify JavaScript to remove `prevCard` function and functionality
  - [ done ] Task 8.4: Modify `nextCard` (or new function for "Next" button) to pick a random card from the current topic on each click
  - [ done ] Task 8.5: Update button event listeners and state management
- [ done ] Task 9: Prevent immediate card repetition
  - [ done ] Task 9.1: Modify `showNewRandomCard` to ensure the newly picked card is different from the current `currentCardIndex` if more than one card exists in the topic.
- [ done ] Task 10: Add "Start from Right Side" switch (Custom UI)
  - [ done ] Task 10.1: Replace checkbox HTML with a custom switch structure (e.g., a div with two selectable options: "Left" and "Right").
  - [ done ] Task 10.2: Add CSS to style the custom switch and highlight the active selection.
  - [ done ] Task 10.3: Modify JavaScript to manage the state of the custom switch (default to "Left").
  - [ done ] Task 10.4: Update `displayCard` to check the custom switch state and apply/remove `flipped` class accordingly.
  - [ done ] Task 10.5: Add event listeners to the switch options to update its state and the currently displayed card's orientation.
- [ done ] Task 11: Implement Two-Screen UI (Topics & Flashcards)
  - [ done ] Task 11.1: Restructure HTML for two main views: Topic Selection and Flashcard View.
  - [ done ] Task 11.2: Add HTML for topic rectangles, back button, and topic name display.
  - [ done ] Task 11.3: Add CSS for new UI elements (topic rectangles, flashcard view header) and view visibility.
  - [ done ] Task 11.4: Implement JavaScript functions to switch between views.
  - [ done ] Task 11.5: Modify JavaScript to dynamically populate topic rectangles instead of a dropdown.
  - [ done ] Task 11.6: Implement click event logic for topic rectangles to switch to flashcard view and load data.
  - [ done ] Task 11.7: Implement "Back" button logic to return to topic selection view.
  - [ done ] Task 11.8: Ensure existing controls (side switch, flip/next buttons) are correctly placed and functional within the flashcard view.
- [ done ] Task 12: Reposition "Start Side" Switch and Remove Label
  - [ done ] Task 12.1: Move the HTML for the side-selector switch into the `flashcard-header`.
  - [ done ] Task 12.2: Remove the "Start with:" label associated with the switch.
  - [ done ] Task 12.3: Adjust CSS for `flashcard-header` and the switch to ensure proper top-right alignment.

## Implementation plan

Detailed description of how the feature will be implemented.

List of tasks in implementation order and detailed description.
1. Task 5: Initialize `TASK.md` file
    a. Task 5.1: Initialize `TASK.md` with the feature name and description.
    b. Task 5.2: Populate "Task status" section with all identified tasks and subtasks, initially marked as "to do".
    c. Task 5.3: Populate "Implementation plan" section, detailing each task and subtask.
    d. Task 5.4: Populate "All relevant files" section, listing files to be created or modified for each task.
2. Task 2: Create JavaScript file for flashcard data (`dictionary.js`)
    a. Task 2.1: Define the JavaScript object structure: An object where keys are topics (strings). Each topic maps to another object where keys are the left side of the flashcard (strings) and values are the right side (strings).
    b. Task 2.2: Add at least one sample topic with a few flashcards to `dictionary.js`.
3. Task 1: Create HTML structure for the flashcard app (`index.html`)
    a. Task 1.1: Set up the main page structure with divs for topic selection, card display area, and buttons.
    b. Task 1.2: Add a dropdown menu (`<select>`) or a list for topic selection.
    c. Task 1.3: Create a div to display the front of the flashcard.
    d. Task 1.4: Create a div to display the back of the flashcard, initially hidden.
    e. Task 1.5: Add buttons for "Flip Card" and "Next Card".
4. Task 3: Implement core flashcard logic (within `<script>` tags in `index.html` or a linked `script.js`)
    a. Task 3.1: Write JavaScript to load the `flashcardData` object from `dictionary.js`.
    b. Task 3.2: Implement a function that populates the topic selector and handles topic changes. When a topic is selected, load its cards.
    c. Task 3.3: Implement a function to display the current card's front side. Manage the current card index.
    d. Task 3.4: Implement a function for the "Flip Card" button to toggle visibility between the card's front and back.
    e. Task 3.5: Implement a function for the "Next Card" button to advance to the next card in the current topic (cycling back to the first if at the end).
5. Task 4: Style the application
    a. Task 4.1: Add CSS rules (either in `<style>` tags in `index.html` or a linked `style.css`) to make the application visually clear and easy to use. Style the card, buttons, and text.
6. Task 6: Implement random card picking
    a. Task 6.1: Add a Fisher-Yates shuffle function to the script in `index.html`.
    b. Task 6.2: In the `loadCardsForTopic` function, after retrieving the card keys for the selected topic, call the shuffle function to randomize their order before the first card is displayed.
7. Task 7: Add more examples to existing topics
    a. Task 7.1: Identify and add 3-5 new relevant question/answer pairs for "Sample Topic 1" in `dictionary.js`.
    b. Task 7.2: Identify and add 3-5 new relevant question/answer pairs for "Sample Topic 2" in `dictionary.js`.
8. Task 8: Refactor navigation and random card selection
    a. Task 8.1: In `index.html`, remove the `<button id="prev-card-btn">` and `<button id="next-card-btn">`.
    b. Task 8.2: In `index.html`, add a new `<button id="next-random-card-btn">Next</button>`.
    c. Task 8.3: In the script in `index.html`, remove the `prevCard` function, its event listener, and references to `prevCardBtn`.
    d. Task 8.4: Modify the `nextCard` function (or create a new one like `showNewRandomCard`). This function should now select a random index from `cardKeys` using `Math.floor(Math.random() * cardKeys.length)` to set `currentCardIndex` before calling `displayCard()`.
    e. Task 8.5: Update the JavaScript to get the new "Next" button element, attach the modified random card selection function to its click event. Adjust `updateButtonStates` accordingly (the new "Next" button should be enabled if cards exist).
9. Task 9: Prevent immediate card repetition
    a. Task 9.1: In the `showNewRandomCard` function in `index.html`, if `cardKeys.length > 1`, store the current `currentCardIndex` before picking a new one. Then, enter a loop that continues to pick a new random index until it is different from the stored previous index. Then update `currentCardIndex` and display the card.
10. Task 10: Add "Start from Right Side" switch (Custom UI)
    a. Task 10.1: In `index.html`, replace the checkbox input with a `div` (e.g., `id="side-selector-switch"`) containing two `span` elements with IDs like `select-left-side` and `select-right-side`, displaying "Left" and "Right" respectively.
    b. Task 10.2: Add CSS rules for `.side-selector-switch`, `.switch-option`, and an `.active-switch-option` class. Style them to resemble a segmented control where the active option is visually distinct (e.g., different background color).
    c. Task 10.3: In JavaScript, get references to these new elements. Initialize a variable `startSide` to `'left'`. Apply the `.active-switch-option` class to the "Left" span by default.
    d. Task 10.4: Modify the `displayCard` function. Instead of checking a checkbox, check the `startSide` variable. If `startSide === 'right'`, add the `flipped` class to `cardElement`; otherwise, remove it.
    e. Task 10.5: Add click event listeners to both `select-left-side` and `select-right-side` spans. When clicked, update the `startSide` variable, toggle the `.active-switch-option` class between the two spans, and if a card is currently displayed, call a function to update its flipped state based on the new `startSide`.
11. Task 11: Implement Two-Screen UI (Topics & Flashcards)
    a. Task 11.1: Restructure HTML for two main views: Topic Selection and Flashcard View.
    b. Task 11.2: Add HTML for topic rectangles, back button, and topic name display.
    c. Task 11.3: Add CSS for new UI elements (topic rectangles, flashcard view header) and view visibility.
    d. Task 11.4: Implement JavaScript functions to switch between views.
    e. Task 11.5: Modify JavaScript to dynamically populate topic rectangles instead of a dropdown.
    f. Task 11.6: Implement click event logic for topic rectangles to switch to flashcard view and load data.
    g. Task 11.7: Implement "Back" button logic to return to topic selection view.
    h. Task 11.8: Ensure the "Start with: Left/Right" switch, "Flip Card", and "Next" buttons are within `#flashcard-view` and function correctly when this view is active.
12. Task 12: Reposition "Start Side" Switch and Remove Label
    a. Task 12.1: In `index.html`, locate the `div` with `id="side-selector-switch"` and its parent `div` within the `.controls` section of `#flashcard-view`. Move the `side-selector-switch` div directly into the `flashcard-header` div, placing it after the `current-topic-display` or the spacer div.
    b. Task 12.2: Remove the `<label for="side-selector-switch">Start with:</label>` element and its parent `div` if it no longer serves a purpose.
    c. Task 12.3: The `flashcard-header` already uses flexbox with `justify-content: space-between`. This should naturally push the switch to the right if it's the last item, or after the centrally displayed topic name. Minor margin/padding adjustments for the switch might be needed for visual appeal.

## All relevant files

List of files which gonna by added or updated.

Task 5.1, 5.2, 5.3, 5.4:
+   TASK.md to add

Task 2.1, 2.2:
+   dictionary.js to add

Task 1.1, 1.2, 1.3, 1.4, 1.5:
+   index.html to add

Task 3.1, 3.2, 3.3, 3.4, 3.5:
+/- index.html to update (if script is inline)
OR
+ script.js to add (if script is external)
+/- index.html to update (to link script.js)

Task 4.1:
+/- index.html to update (if style is inline or in head)
OR
+ style.css to add (if style is external)
+/- index.html to update (to link style.css)

Task 6.1, 6.2:
+/- index.html to update (JavaScript logic)

Task 7.1, 7.2:
+/- dictionary.js to update (add more data)

Task 8.1, 8.2, 8.3, 8.4, 8.5:
+/- index.html to update (HTML and JavaScript logic)

Task 9.1:
+/- index.html to update (JavaScript logic)

Task 10.1, 10.2, 10.3, 10.4, 10.5:
+/- index.html to update (HTML, CSS, and JavaScript logic)

Task 11.1 - 11.8:
+/- index.html to update (Major HTML, CSS, and JavaScript refactor)

Task 12.1, 12.2, 12.3:
+/- index.html to update (HTML and CSS changes) 