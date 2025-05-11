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
- [ done ] Task 13: Implement Spaced Repetition System (SRS) with 5 Boxes
  - [ done ] Task 13.1: (JS) Define data structure for `currentTopicSRSData` (card object with question, answer, box number).
  - [ done ] Task 13.2: (JS) Modify `loadCardsForTopic` to initialize all cards in a topic to Box 1 within `currentTopicSRSData`.
  - [ done ] Task 13.3: (HTML) Add UI elements for the 5 SRS boxes (e.g., divs to show "Box 1: [count]").
  - [ done ] Task 13.4: (HTML) Add "I know it!" and "I forgot :c" buttons to the flashcard view.
  - [ done ] Task 13.5: (CSS) Style the SRS boxes and new buttons.
  - [ done ] Task 13.6: (JS) Implement `updateBoxDisplay()` to show card counts in each box UI element.
  - [ done ] Task 13.7: (JS) Implement `handleKnowIt()`: increment card's box (max 5), update display, show new card.
  - [ done ] Task 13.8: (JS) Implement `handleForgot()`: decrement card's box (min 1), update display, show new card.
  - [ done ] Task 13.9: (JS) Refactor `showNewRandomCard()` to select cards from the lowest non-empty box, preventing immediate repetition within that box.
  - [ done ] Task 13.10: (JS) Update `displayCard` to use `currentTopicSRSData`.
  - [ done ] Task 13.11: (JS) Update `updateButtonStates` for new SRS buttons and existing buttons based on SRS state.
  - [ done ] Task 13.12: (JS) Remove old "Next" button (`nextRandomCardBtn`) from JS logic.
- [ done ] Task 14: Persist SRS Box Data in localStorage
  - [ done ] Task 14.1: (JS) Create `saveSRStoLocalStorage(topicName, srsCardStates)` function.
  - [ done ] Task 14.2: (JS) Create `loadSRSfromLocalStorage(topicName)` function.
  - [ done ] Task 14.3: (JS) Modify `loadCardsForTopic` to load from localStorage if available, otherwise initialize to Box 1 and save.
  - [ done ] Task 14.4: (JS) Modify `handleKnowIt` and `handleForgot` to save SRS state after box changes.
  - [ done ] Task 14.5: (HTML) Add a "Clear All Progress" button to the topic selection view.
  - [ done ] Task 14.6: (CSS) Style the new button.
  - [ done ] Task 14.7: (JS) Create `handleClearAllSRSData` function to remove all `srsData_` keys from localStorage and refresh view.
  - [ done ] Task 14.8: (JS) Add event listener for the "Clear All Progress" button.
- [ done ] Task 15: Refine SRS Logic for "I forgot" and Box Prioritization
  - [ done ] Task 15.1: (JS) Modify `handleForgot()`: The card *is* moved to `box i-1` (if `i > 1`). `previousCardId` is set. State is saved. `showNewRandomCard()` is called. The key change is how `showNewRandomCard` then behaves.
  - [ done ] Task 15.2: (JS) Introduce a new global JavaScript variable: `let activeLearningBox = 1;` (or initialized dynamically).
  - [ done ] Task 15.3: (JS) In `loadCardsForTopic`, after `currentTopicSRSData` is populated (from source or localStorage) and saved, iterate from box `b=1` to `5`. The first `b` for which `currentTopicSRSData.some(card => card.box === b)` is true becomes the new `activeLearningBox`. If no cards, set `activeLearningBox` to a state indicating no active box (e.g., 0 or null).
  - [ done ] Task 15.4: (JS) Refactor `showNewRandomCard`:
      i. Identify `cardsInActiveBox = currentTopicSRSData.filter(c => c.box === activeLearningBox)`.
      ii. Filter `cardsInActiveBox` to exclude `previousCardId` IF `previousCardId`'s original card object (found by ID in `currentTopicSRSData`) was also in `activeLearningBox` AND if `cardsInActiveBox.length > 1`. Let this be `selectableFromActiveBox`.
      iii. If `selectableFromActiveBox` is not empty, pick a random card from it, set `currentCardIndex`, call `displayCard()`, and return.
      iv. Else (active box depleted or only had `previousCardId`), scan for a new `activeLearningBox`: Loop `b` from 1 to 5. Find first `b` where `currentTopicSRSData.some(c => c.box === b)` is true. 
      v. If a new `activeLearningBox` `b` is found: set `activeLearningBox = b`, get all cards in this new box, pick one randomly (no need for `previousCardId` check here as we changed boxes), set `currentCardIndex`, call `displayCard()`, and return.
      vi. Else (no cards in any box 1-5), set `currentCardIndex = -1`, call `displayCard()`, and return.
  - [ done ] Task 15.2 from previous task list (Confirm topic re-entry correctly starts review from earliest box) is naturally handled by `loadCardsForTopic` re-calculating `activeLearningBox` and resetting `previousCardId`.
- [ done ] Task 16: Relocate and Refine "Clear Progress" Button
  - [ done ] Task 16.1: (HTML) Move the clear progress button from `topic-selection-view` to `flashcard-view` (e.g., below SRS boxes).
  - [ done ] Task 16.2: (HTML) Rename button text to "Reset Topic Progress".
  - [ done ] Task 16.3: (JS) Rename `handleClearAllSRSData` to `handleClearCurrentTopicSRSData`.
  - [ done ] Task 16.4: (JS) Modify the renamed function to remove only `localStorage` for the `currentTopic`.
  - [ done ] Task 16.5: (JS) After clearing, the function should reload the current topic by calling `loadCardsForTopic()` (it implicitly uses `currentTopic`).
  - [ done ] Task 16.6: (JS) Update `updateButtonStates` to manage enable/disable state of this button (enabled in flashcard view).
- [ done ] Task 17: Refine "Reset Topic Progress" Button to Icon in Header
  - [ done ] Task 17.1: (HTML) Remove existing "Reset Topic Progress" button and its container.
  - [ done ] Task 17.2: (HTML) Add a new icon button (e.g., using ↻ symbol) with ID `clear-srs-storage-btn` inside `.flashcard-header` next to the topic name.
  - [ done ] Task 17.3: (CSS) Style the new icon button for subtle appearance and correct alignment in the header.
  - [ done ] Task 17.4: (JS) Ensure existing JS for this button ID works as intended with the new element.
- [ done ] Task 18: Refine Flashcard Header Layout
  - [ done ] Task 18.1: (HTML) Group topic name and refresh icon in a new container div within `.flashcard-header`
  - [ done ] Task 18.2: (CSS) Style the new container to center its content (topic name + icon) and use `flex-grow` to occupy middle space
  - [ done ] Task 18.3: (CSS) Adjust styles for topic name and refresh icon for better alignment and spacing within their new container
- [ done ] Task 19: Advanced Header Centering with Absolute Positioning
  - [ done ] Task 19.1: (CSS) Modify `.flashcard-header` to be `position: relative`.
  - [ done ] Task 19.2: (CSS) Absolutely position `#back-to-topics-btn` to the left and `#side-selector-switch` to the right, vertically centered.
  - [ done ] Task 19.3: (CSS) Ensure `.topic-title-wrapper` (containing topic name and refresh icon) correctly centers its content across the full header width, accounting for the absolutely positioned elements.
- [ done ] Task 20: Adjust Flashcard Header Spacing
  - [ done ] Task 20.1: (CSS) Set `margin-bottom: 0;` for `.flashcard-header`
  - [ done ] Task 20.2: (CSS) Remove `padding-bottom: 10px;` from `.flashcard-header`
- [ done ] Task 21: Improve Styles and Responsiveness
  - [ done ] Task 21.1: (CSS) Apply a more modern font stack and base line-height.
  - [ done ] Task 21.2: (CSS) Add `box-sizing: border-box;` globally.
  - [ done ] Task 21.3: (CSS) Add media queries to adjust layout and font sizes for smaller screens (e.g., topic cards, SRS boxes, header elements, card text).
  - [ done ] Task 21.4: (CSS) Refine button styles (padding, hover/active states) for consistency and usability.
  - [ done ] Task 21.5: (CSS) General review of spacing and visual hierarchy.
- [ done ] Task 22: Relocate SRS Box Display to Bottom
  - [ done ] Task 22.1: (HTML) Move the `#srs-boxes-container` div to below the `.navigation-buttons` div.
  - [ done ] Task 22.2: (CSS) Adjust margins and borders for `#srs-boxes-container` for its new position at the bottom.
- [ done ] Task 23: UI and Styling Refinements
  - [ done ] Task 23.1: (CSS) Remove `padding-bottom` from `.flashcard-header`.
  - [ done ] Task 23.2: (HTML & JS) Display the current `activeLearningBox` number in the UI.
  - [ done ] Task 23.3: (CSS) Differentiate card front/back with background colors.
  - [ done ] Task 23.4: (CSS) Make the Left/Right switch options use these same background colors when active.
- [ done ] Task 24: Change Active Learning Box Indication to Box Highlighting
  - [ done ] Task 24.1: (HTML) Remove the `<p id=\"current-learning-box-display\" class=\"learning-box-info\"></p>` element.
  - [ done ] Task 24.2: (CSS) Remove the `.learning-box-info` CSS rule. Create a new rule for `.srs-box.active-srs-box` (e.g., `background-color: #cce5ff; color: #004085; border-color: #b8daff; font-weight: bold;`).
  - [ done ] Task 24.3: (CSS) Adjust `.topic-title-wrapper` if its `flex-direction` was only for the removed text.
  - [ done ] Task 24.4: (JS) Remove JS related to `currentLearningBoxDisplay` text element.
  - [ done ] Task 24.5: (JS) Modify `updateBoxDisplay()` to add/remove `.active-srs-box` class from the correct SRS box div based on `activeLearningBox`.
- [ done ] Task 25: Fix Side Switch Display & Remove Flip Card Button
  - [ done ] Task 25.1: (CSS) Correct CSS for `.side-selector-switch` to ensure visibility and right-alignment in the header.
  - [ done ] Task 25.2: (HTML) Remove the "Flip Card" button.
  - [ done ] Task 25.3: (JS) Remove `flipCardBtn` constant, its event listener, and its state management in `updateButtonStates`. (Keep `flipCard()` if card click still flips).
- [ done ] Task 26: Adjust SRS Button Layout (Forgot/Know) - Persistent Side-by-Side Full Width
  - [ done ] Task 26.1: (CSS) Configure `.navigation-buttons` for flex layout to support two full-width-sharing child buttons.
  - [ done ] Task 26.2: (CSS) Apply `flex-grow: 1` and `flex-basis: 0` to `#forgot-btn` and `#know-it-btn` to make them share the full width.
  - [ done ] Task 26.3: (CSS) Ensure these styles override any media query stacking for these specific buttons, so they remain side-by-side on all screen sizes.

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
13. Task 13: Implement Spaced Repetition System (SRS) with 5 Boxes
    a. Task 13.1: In JavaScript, when a topic is loaded, instead of just `cardKeys`, create an array `currentTopicSRSData`. Each element will be an object like `{ question: "...", answer: "...", box: 1, id: "unique_id_for_card" }`. The `id` can be the question string if unique, or a generated ID.
    b. Task 13.2: Modify `loadCardsForTopic` to iterate through `flashcardData[currentTopic]`, and for each card, populate `currentTopicSRSData` with its `question`, `answer`, and an initial `box: 1`.
    c. Task 13.3: In `flashcard-view` HTML, add a new div (e.g., `<div id="srs-boxes-container">`) above the `flashcard-area`. This container will hold 5 child divs (e.g., class `.srs-box`, with IDs like `srs-box-1`). Each will display text like "Box 1 (0)".
    d. Task 13.4: In `flashcard-view` HTML, within `.navigation-buttons`, remove the old "Next" button and add two new buttons: `<button id="forgot-btn">I forgot :c</button>` and `<button id="know-it-btn">I know it!</button>`.
    e. Task 13.5: Add CSS to style `#srs-boxes-container` (e.g., flex display, space around) and `.srs-box` (padding, border, margin, min-width). Style the new `#know-it-btn` and `#forgot-btn`.
    f. Task 13.6: Create `updateBoxDisplay()`. This function will iterate 1 through 5, count cards in `currentTopicSRSData` for each box, and update the text content of the corresponding `#srs-box-N` UI element.
    g. Task 13.7: Create `handleKnowIt()`. If `currentCardIndex` is valid and `currentTopicSRSData[currentCardIndex]` exists: get the card, increment its `box` property (if `box < 5`, else it stays 5). Call `updateBoxDisplay()` (via `displayCard`), then `showNewRandomCard()`.
    h. Task 13.8: Create `handleForgot()`. If `currentCardIndex` is valid and `currentTopicSRSData[currentCardIndex]` exists: get the card, decrement its `box` property (if `box > 1`, else it stays 1). Call `updateBoxDisplay()` (via `displayCard`), then `showNewRandomCard()`.
    i. Task 13.9: Refactor `showNewRandomCard()`. Loop from box `b = 1` to `5`. Filter `currentTopicSRSData` for cards where `card.box === b`. If this filtered list (`eligibleCards`) is not empty, pick a random card from it. Ensure it's not the `previousCardId` (if `eligibleCards.length > 1`). Update `currentCardIndex` to the index of the chosen card in the *original* `currentTopicSRSData`. If all boxes are empty, display a completion message.
    j. Task 13.10: Modify `displayCard()` to get `question` and `answer` from `currentTopicSRSData[currentCardIndex]`. `cardKeys` will no longer be used directly for display.
    k. Task 13.11: Adjust `updateButtonStates()`: "Know it" and "Forgot" buttons are enabled if a card is displayed. "Flip" button also depends on card display.
    l. Task 13.12: (JS) Remove all references to `nextRandomCardBtn` from JS, including its `getElementById` and event listener (if any was re-added).
14. Task 14: Persist SRS Box Data in localStorage
    a. Task 14.1: (JS) `saveSRStoLocalStorage(topicName, srsCardStates)`: Takes the `currentTopicSRSData` (which contains full card objects). It should map this to an array of simpler objects `[{id, box}]` to store. It will then `JSON.stringify` this array and save it to `localStorage` under the key `