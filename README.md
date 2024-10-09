
# Modal Project


## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Features](#features)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Code Explanation](#code-explanation)
  - [JavaScript](#javascript-appjs)
  - [HTML](#html-indexhtml)


## Project Overview
This project demonstrates a basic implementation of a modal in a web page using HTML, CSS, and JavaScript. The modal pops up when the user clicks the "Open Modal" button and can be closed by clicking the close (X) button. This simple project is a great introduction to working with modals and event listeners in JavaScript. A good example of a modal window would be if a user made changes in a site without saving them and tried to go to another page. You can create a modal window that warns them to save their changes or else that information will be lost.

## Technologies Used
HTML5
CSS3
JavaScript (ES6+)
Font Awesome (for icons)

## Features
Displays a modal window when the "Open Modal" button is clicked.
Allows the user to close the modal by clicking the close button (X).
Simple, clean, and responsive design.

## How It Works
*Modal Trigger*: The modal is triggered by a button with the class .modal-btn. When clicked, this button adds the open-modal class to the modal overlay, making it visible.

*Closing the Modal*: When the close button (.close-btn) is clicked, it removes the open-modal class from the modal overlay, hiding it from view.

*CSS Transitions*: CSS is used to control the appearance of the modal when the class open-modal is added or removed. The modal fades in and out based on its visibility state.

## Usage
To use this modal:

Click the "Open Modal" button to trigger the modal overlay.
Interact with the modal content.
Click the close button (X) to hide the modal and return to the main content.

## Project Structure
index.html: Contains the structure of the webpage, including the button to trigger the modal and the modal itself.
styles.css: Contains the styles for the layout and design of the webpage, including the modal's appearance.
app.js: Contains the JavaScript code that adds the interaction logic (opening and closing the modal).

## Code Explanation

### JavaScript (`app.js`):

The JavaScript file `app.js` controls the functionality of the modal, enabling it to open and close based on user interactions.

```javascript
const modalBtn = document.querySelector('.modal-btn');
const modalOverlay = document.querySelector('.modal-overlay');
const closeBtn = document.querySelector('.close-btn');

// Open modal on button click
modalBtn.addEventListener('click', function(){
    modalOverlay.classList.add("open-modal");
})

// Close modal on close button click
closeBtn.addEventListener('click', function(){
    modalOverlay.classList.remove('open-modal');
})
```

- **modalBtn**: Selects the button with the class `.modal-btn`, which triggers the modal to open.

- **modalOverlay**: Selects the overlay element with the class `.modal-overlay`, which contains the modal content.

- **closeBtn**: Selects the close button within the modal.

#### Event Listeners:
- **Open Modal**: When the `.modal-btn` is clicked, the `open-modal` class is added to `modalOverlay`, making it visible.

- **Close Modal**: When the close button is clicked (`.close-btn`), the `open-modal` class is removed from `modalOverlay`, hiding the modal from view.

### HTML (`index.html`):

The HTML file `index.html` provides the structure of the webpage, including the modal trigger button and the modal itself.

```html
<header class="hero">
  <div class="banner">
    <h1>Modal project</h1>
    <button class="btn modal-btn">open modal</button>
  </div>
</header>

<div class="modal-overlay">
  <div class="modal-container">
    <h3>modal content</h3>
    <button class="close-btn">
      <i class="fas fa-times"></i>
    </button>
  </div>
</div>
```

- **modal-btn**: Button that triggers the modal to open when clicked.

- **modal-overlay**: Overlay that contains the modal content.

- **close-btn**: Button inside the modal that allows the user to close it.

### CSS (`styles.css`):

The CSS file `styles.css` provides the styles for the modal and its overlay to control their appearance and behavior.

```css
/* Styles for modal overlay */
.modal-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  justify-content: center;
  align-items: center;
}

/* Styles for modal container */
.modal-container {
  background: white;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}

/* Styles for close button */
.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 24px;
  color: #888;
}
```

- **modal-overlay**: Provides a semi-transparent background that covers the entire screen when the modal is open.

- **modal-container**: Styles the container for modal content, centered within the overlay.

- **close-btn**: Styles the close button (`X`) inside the modal.
