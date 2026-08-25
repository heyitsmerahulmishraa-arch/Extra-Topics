# Real-World JavaScript Skills

## Form Validation
Form validation is a crucial aspect of web development that ensures user input meets specific criteria before being submitted to the server. It helps improve user experience, prevent errors, and enhance security by validating data on the client side. JavaScript provides various methods and techniques for implementing form validation, including built-in HTML5 validation attributes, custom validation functions, and event handling.

### Example of Form Validation
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation Example</title>
    <style>
        .error {
            color: red;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <form id="myForm">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <span class="error" id="usernameError"></span>
        <br><br>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <span class="error" id="emailError"></span>
        <br><br>

        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required minlength="6">
        <span class="error" id="passwordError"></span>
        <br><br>

        <button type="submit">Submit</button>
    </form>

    <script>
        const form = document.getElementById('myForm');
        const usernameError = document.getElementById('usernameError');
        const emailError = document.getElementById('emailError');
        const passwordError = document.getElementById('passwordError');

        form.addEventListener('submit', function(event) {
            let isValid = true;

            // Validate username
            if (form.username.value.trim() === '') {
                usernameError.textContent = 'Username is required.';
                isValid = false;
            } else {
                usernameError.textContent = '';
            }

            // Validate email
            if (form.email.value.trim() === '') {
                emailError.textContent = 'Email is required.';
                isValid = false;
            } else if (!/\S+@\S+\.\S+/.test(form.email.value)) {
                emailError.textContent = 'Please enter a valid email address.';
                isValid = false;
            } else {
                emailError.textContent = '';
            }

            // Validate password
            if (form.password.value.trim() === '') {
                passwordError.textContent = 'Password is required.';
                isValid = false;
            } else if (form.password.value.length < 6) {
                passwordError.textContent = 'Password must be at least 6 characters long.';
                isValid = false;
            } else {
                passwordError.textContent = '';
            }

            // Prevent form submission if validation fails
            if (!isValid) {
                event.preventDefault();
            }
        });
    </script>
</body>
</html>
```

## Search Functionality
Search functionality is an essential feature in web applications that allows users to find specific information quickly and efficiently. Implementing search functionality involves capturing user input, filtering data based on the input, and displaying the results dynamically. JavaScript provides various methods for implementing search functionality, including event handling, array methods, and DOM manipulation.

### Example of Search Functionality
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Search Functionality Example</title>
    <style>
        .result {
            margin: 5px 0;
        }
    </style>
</head>
<body>
    <input type="text" id="searchInput" placeholder="Search...">
    <div id="results"></div>

    <script>
        const data = [
            'Apple',
            'Banana',
            'Cherry',
            'Date',
            'Elderberry',
            'Fig',
            'Grape',
            'Honeydew'
        ];

        const searchInput = document.getElementById('searchInput');
        const resultsDiv = document.getElementById('results');

        searchInput.addEventListener('input', function() {
            const query = searchInput.value.toLowerCase();
            resultsDiv.innerHTML = '';

            const filteredResults = data.filter(item => item.toLowerCase().includes(query));

            if (filteredResults.length > 0) {
                filteredResults.forEach(item => {
                    const resultItem = document.createElement('div');
                    resultItem.className = 'result';
                    resultItem.textContent = item;
                    resultsDiv.appendChild(resultItem);
                });
            } else {
                resultsDiv.textContent = 'No results found.';
            }
        });
    </script>
</body>
</html>
```

## Pagination
Pagination is a technique used in web applications to divide large sets of data into smaller, manageable chunks, allowing users to navigate through the data easily. It improves user experience by reducing the amount of information displayed at once and providing navigation controls to access different pages of data. JavaScript can be used to implement pagination by dynamically generating page links and displaying the corresponding data for each page.

### Example of Pagination
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pagination Example</title>
    <style>
        .page-link {
            margin: 0 5px;
            cursor: pointer;
            color: blue;
        }
        .page-link.active {
            font-weight: bold;
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div id="dataContainer"></div>
    <div id="paginationControls"></div>

    <script>
        const data = Array.from({ length: 100 }, (_, i) => `Item ${i + 1}`);
        const itemsPerPage = 10;
        let currentPage = 1;

        function displayData(page) {
            const startIndex = (page - 1) * itemsPerPage;
            const endIndex = startIndex + itemsPerPage;
            const paginatedData = data.slice(startIndex, endIndex);

            const dataContainer = document.getElementById('dataContainer');
            dataContainer.innerHTML = '';
            paginatedData.forEach(item => {
                const itemDiv = document.createElement('div');
                itemDiv.textContent = item;
                dataContainer.appendChild(itemDiv);
            });
        }

        function setupPagination() {
            const totalPages = Math.ceil(data.length / itemsPerPage);
            const paginationControls = document.getElementById('paginationControls');
            paginationControls.innerHTML = '';

            for (let i = 1; i <= totalPages; i++) {
                const pageLink = document.createElement('span');
                pageLink.className = 'page-link';
                pageLink.textContent = i;
                if (i === currentPage) {
                    pageLink.classList.add('active');
                }
                pageLink.addEventListener('click', () => {
                    currentPage = i;
                    displayData(currentPage);
                    setupPagination();
                });
                paginationControls.appendChild(pageLink);
            }
        }

        // Initial display
        displayData(currentPage);
        setupPagination();
    </script>
</body>
</html>
```

## Infinite Scrolling
Infinite scrolling is a web design technique that allows users to continuously load and view content as they scroll down a page, without the need for pagination or manual navigation. It provides a seamless user experience by dynamically loading additional content when the user reaches the bottom of the page. JavaScript can be used to implement infinite scrolling by detecting the user's scroll position and fetching new data when necessary.

### Example of Infinite Scrolling
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Infinite Scrolling Example</title>
    <style>
        .item {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <div id="contentContainer"></div>
    <div id="loadingIndicator" style="display: none;">Loading...</div>

    <script>
        const contentContainer = document.getElementById('contentContainer');
        const loadingIndicator = document.getElementById('loadingIndicator');
        let itemCount = 0;
        const itemsPerLoad = 20;

        function loadMoreItems() {
            loadingIndicator.style.display = 'block';
            setTimeout(() => {
                for (let i = 0; i < itemsPerLoad; i++) {
                    itemCount++;
                    const itemDiv = document.createElement('div');
                    itemDiv.className = 'item';
                    itemDiv.textContent = `Item ${itemCount}`;
                    contentContainer.appendChild(itemDiv);
                }
                loadingIndicator.style.display = 'none';
            }, 1000); // Simulate network delay
        }

        window.addEventListener('scroll', () => {
            if (window.innerHeight + window.scrollY >= document.body.offsetHeight - 100) {
                loadMoreItems();
            }
        });

        // Initial load
        loadMoreItems();
    </script>
</body>
</html>
```

## Auto-complete
Auto-complete is a user interface feature that provides suggestions to users as they type in an input field, helping them complete their input more quickly and accurately. It enhances user experience by reducing typing effort and minimizing errors. JavaScript can be used to implement auto-complete functionality by capturing user input, filtering a list of suggestions based on the input, and displaying the matching suggestions dynamically.

### Example of Auto-complete
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Auto-complete Example</title>
    <style>
        .autocomplete-suggestions {
            border: 1px solid #ccc;
            max-height: 150px;
            overflow-y: auto;
            position: absolute;
            background-color: white;
            z-index: 1000;
        }
        .autocomplete-suggestion {
            padding: 5px;
            cursor: pointer;
        }
        .autocomplete-suggestion:hover {
            background-color: #f0f0f0;
        }
    </style>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const suggestions = ['Apple', 'Banana', 'Cherry', 'Date', 'Elderberry', 'Fig', 'Grape', 'Honeydew'];
            const input = document.getElementById('autocompleteInput');
            const suggestionsContainer = document.createElement('div');
            suggestionsContainer.className = 'autocomplete-suggestions';
            document.body.appendChild(suggestionsContainer);

            input.addEventListener('input', () => {
                const query = input.value.toLowerCase();
                suggestionsContainer.innerHTML = '';
                if (query) {
                    const filteredSuggestions = suggestions.filter(item => item.toLowerCase().includes(query));
                    filteredSuggestions.forEach(item => {
                        const suggestionDiv = document.createElement('div');
                        suggestionDiv.className = 'autocomplete-suggestion';
                        suggestionDiv.textContent = item;
                        suggestionDiv.addEventListener('click', () => {
                            input.value = item;
                            suggestionsContainer.innerHTML = '';
                        });
                        suggestionsContainer.appendChild(suggestionDiv);
                    });
                }
            });

            document.addEventListener('click', (event) => {
                if (event.target !== input) {
                    suggestionsContainer.innerHTML = '';
                }
            });
        });
    </script>
</head>
<body>
    <input type="text" id="autocompleteInput" placeholder="Type to search...">  
</body>
</html>
```

## Image Preview
Image preview is a feature that allows users to see a visual representation of an image before it is uploaded or submitted. This enhances user experience by providing immediate feedback and ensuring that the correct image is selected. JavaScript can be used to implement image preview functionality by capturing the file input change event, reading the selected image file, and displaying it in an image element.

### Example of Image Preview
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Preview Example</title>
    <style>
        #imagePreview {
            max-width: 300px;
            max-height: 300px;
            margin-top: 10px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <input type="file" id="imageInput" accept="image/*">
    <img id="imagePreview" src="" alt="Image Preview">

    <script>
        const imageInput = document.getElementById('imageInput');
        const imagePreview = document.getElementById('imagePreview');

        imageInput.addEventListener('change', () => {
            const file = imageInput.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = (e) => {
                    imagePreview.src = e.target.result;
                };
                reader.readAsDataURL(file);
            } else {
                imagePreview.src = '';
            }
        });
    </script>
</body>
</html>
```

## File upload
File upload is a common feature in web applications that allows users to select and upload files from their local device to a server. It is often used for submitting documents, images, videos, or other types of files. JavaScript can be used to enhance the file upload experience by providing features such as drag-and-drop support, progress indicators, and client-side validation before the file is sent to the server.

### Example of File Upload
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>File Upload Example</title>
    <style>
        #fileInput {
            margin-bottom: 10px;
        }
        #uploadStatus {
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <input type="file" id="fileInput" multiple>
    <button id="uploadButton">Upload</button>
    <div id="uploadStatus"></div>

    <script>
        const fileInput = document.getElementById('fileInput');
        const uploadButton = document.getElementById('uploadButton');
        const uploadStatus = document.getElementById('uploadStatus');

        uploadButton.addEventListener('click', () => {
            const files = fileInput.files;
            if (files.length === 0) {
                uploadStatus.textContent = 'Please select a file to upload.';
                return;
            }

            const formData = new FormData();
            for (let i = 0; i < files.length; i++) {
                formData.append('files[]', files[i]);
            }

            // Simulating file upload (replace with actual server endpoint)
            fetch('/upload', {
                method: 'POST',
                body: formData
            })
            .then(response => response.json())
            .then(data => {
                uploadStatus.textContent = 'Files uploaded successfully!';
                console.log(data);
            })
            .catch(error => {
                uploadStatus.textContent = 'Error uploading files.';
                console.error(error);
            });
        });
    </script>
</body>
</html>
```

## Drag and Drop
Drag and drop is a user interface feature that allows users to interact with elements on a web page by clicking and dragging them to a different location. It enhances user experience by providing a more intuitive way to move or rearrange items. JavaScript can be used to implement drag-and-drop functionality by handling mouse events and updating the position of elements based on user interactions.


### Example of Drag and Drop
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Drag and Drop Example</title>
    <style>
        .draggable {
            width: 100px;
            height: 100px;
            background-color: lightblue;
            margin: 10px;
            display: inline-block;
            cursor: grab;
        }
        .dropzone {
            width: 300px;
            height: 300px;
            border: 2px dashed #ccc;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="draggable" draggable="true" id="dragItem">Drag me</div>
    <div class="dropzone" id="dropZone">Drop here</div>

    <script>
        const dragItem = document.getElementById('dragItem');
        const dropZone = document.getElementById('dropZone');

        dragItem.addEventListener('dragstart', (event) => {
            event.dataTransfer.setData('text/plain', event.target.id);
        });

        dropZone.addEventListener('dragover', (event) => {
            event.preventDefault(); // Allow dropping
        });

        dropZone.addEventListener('drop', (event) => {
            event.preventDefault();
            const draggedItemId = event.dataTransfer.getData('text/plain');
            const draggedItem = document.getElementById(draggedItemId);
            dropZone.appendChild(draggedItem); // Move the dragged item to the drop zone
        });
    </script>
</body>
</html>
```

## Modal Systems
A modal system is a user interface component that displays content in a layer above the main page, often used for dialogs, forms, or notifications. Modals can be triggered by user actions and typically require the user to interact with them before returning to the main content. JavaScript can be used to create and manage modals by handling events, toggling visibility, and managing focus.

### Example of Modal System
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modal System Example</title>
    <style>
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.5);
        }
        .modal-content {
            background-color: #fff;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 500px;
        }
        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }
        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <button id="openModalBtn">Open Modal</button>

    <div id="myModal" class="modal">
        <div class="modal-content">
            <span class="close" id="closeModalBtn">&times;</span>
            <h2>Modal Title</h2>
            <p>This is a simple modal example.</p>
        </div>
    </div>

    <script>
        const openModalBtn = document.getElementById('openModalBtn');
        const closeModalBtn = document.getElementById('closeModalBtn');
        const modal = document.getElementById('myModal');

        openModalBtn.addEventListener('click', () => {
            modal.style.display = 'block';
        });

        closeModalBtn.addEventListener('click', () => {
            modal.style.display = 'none';
        });

        window.addEventListener('click', (event) => {
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        });
    </script>
</body>
</html>
```

## Tabs
Tabs are a user interface component that allows users to switch between different sections of content within the same page. Each tab corresponds to a specific content area, and clicking on a tab displays the associated content while hiding the others. JavaScript can be used to implement tab functionality by handling click events and toggling the visibility of content sections.

### Example of Tabs
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tabs Example</title>
    <style>
        .tab {
            display: inline-block;
            padding: 10px 20px;
            cursor: pointer;
            background-color: #f1f1f1;
            border: 1px solid #ccc;
            margin-right: -1px;
        }
        .tab.active {
            background-color: #fff;
            border-bottom: none;
        }
        .tab-content {
            display: none;
            padding: 20px;
            border: 1px solid #ccc;
            border-top: none;
        }
        .tab-content.active {
            display: block;
        }
    </style>
</head>
<body>
    <div class="tabs">
        <div class="tab active" data-tab="tab1">Tab 1</div>
        <div class="tab" data-tab="tab2">Tab 2</div>
        <div class="tab" data-tab="tab3">Tab 3</div>
    </div>

    <div id="tab1" class="tab-content active">
        <h2>Content for Tab 1</h2>
        <p>This is the content for Tab 1.</p>
    </div>
    <div id="tab2" class="tab-content">
        <h2>Content for Tab 2</h2>
        <p>This is the content for Tab 2.</p>
    </div>
    <div id="tab3" class="tab-content">
        <h2>Content for Tab 3</h2>
        <p>This is the content for Tab 3.</p>
    </div>

    <script>
        const tabs = document.querySelectorAll('.tab');
        const tabContents = document.querySelectorAll('.tab-content');

        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                // Remove active class from all tabs and contents
                tabs.forEach(t => t.classList.remove('active'));
                tabContents.forEach(tc => tc.classList.remove('active'));

                // Add active class to the clicked tab and corresponding content
                tab.classList.add('active');
                document.getElementById(tab.dataset.tab).classList.add('active');
            });
        });
    </script>
</body>
</html>
```

## Accordions
Accordions are a user interface component that allows users to expand and collapse sections of content. Each section typically has a header that can be clicked to reveal or hide the associated content. Accordions are useful for organizing information in a compact and user-friendly manner. JavaScript can be used to implement accordion functionality by handling click events and toggling the visibility of content sections.

### Example of Accordions
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accordion Example</title>
    <style>
        .accordion {
            background-color: #f1f1f1;
            cursor: pointer;
            padding: 10px;
            border: 1px solid #ccc;
            margin-bottom: 5px;
        }
        .accordion-content {
            display: none;
            padding: 10px;
            border: 1px solid #ccc;
            border-top: none;
        }
    </style>
</head>
<body>
    <div class="accordion">Section 1</div>
    <div class="accordion-content">
        <p>This is the content for Section 1.</p>
    </div>

    <div class="accordion">Section 2</div>
    <div class="accordion-content">
        <p>This is the content for Section 2.</p>
    </div>

    <div class="accordion">Section 3</div>
    <div class="accordion-content">
        <p>This is the content for Section 3.</p>
    </div>

    <script>
        const accordions = document.querySelectorAll('.accordion');

        accordions.forEach(accordion => {
            accordion.addEventListener('click', () => {
                // Toggle the active state of the clicked accordion
                accordion.classList.toggle('active');

                // Toggle the display of the corresponding content
                const content = accordion.nextElementSibling;
                if (content.style.display === 'block') {
                    content.style.display = 'none';
                } else {
                    content.style.display = 'block';
                }
            });
        });
    </script>
</body>
</html>
```

## Dropdowns
Dropdowns are a user interface component that allows users to select an option from a list of choices. When a user clicks on the dropdown, a list of options is displayed, and the user can select one of them. Dropdowns are commonly used in forms and navigation menus. JavaScript can be used to enhance dropdown functionality by handling click events, toggling visibility, and managing selected options.

### Example of Dropdowns
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dropdown Example</title>
    <style>
        .dropdown {
            position: relative;
            display: inline-block;
        }
        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #f1f1f1;
            min-width: 160px;
            box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
            z-index: 1;
        }
        .dropdown-content div {
            padding: 12px 16px;
            cursor: pointer;
        }
        .dropdown-content div:hover {
            background-color: #ddd;
        }
    </style>
</head>
<body>
    <div class="dropdown">
        <button id="dropdownBtn">Select an option</button>
        <div class="dropdown-content" id="dropdownContent">
            <div>Option 1</div>
            <div>Option 2</div>
            <div>Option 3</div>
        </div>
    </div>

    <script>
        const dropdownBtn = document.getElementById('dropdownBtn');
        const dropdownContent = document.getElementById('dropdownContent');

        dropdownBtn.addEventListener('click', () => {
            dropdownContent.style.display = dropdownContent.style.display === 'block' ? 'none' : 'block';
        });

        // Close the dropdown if the user clicks outside of it
        window.addEventListener('click', (event) => {
            if (!event.target.matches('#dropdownBtn')) {
                dropdownContent.style.display = 'none';
            }
        });

        // Handle option selection
        const options = dropdownContent.querySelectorAll('div');
        options.forEach(option => {
            option.addEventListener('click', () => {
                dropdownBtn.textContent = option.textContent;
                dropdownContent.style.display = 'none';
            });
        });
    </script>
</body>
</html>
```

## Toast notifications
Toast notifications are brief, auto-expiring messages that appear on the screen to provide feedback or information to users. They are commonly used to inform users about the success or failure of an action, such as form submissions or data updates. JavaScript can be used to create and manage toast notifications by dynamically generating notification elements, controlling their display duration, and handling user interactions.

### Example of Toast Notifications
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toast Notifications Example</title>
    <style>
        .toast {
            visibility: hidden;
            min-width: 250px;
            margin-left: -125px;
            background-color: #333;
            color: #fff;
            text-align: center;
            border-radius: 2px;
            padding: 16px;
            position: fixed;
            z-index: 1;
            left: 50%;
            bottom: 30px;
            font-size: 17px;
        }
        .toast.show {
            visibility: visible;
            animation: fadein 0.5s, fadeout 0.5s 2.5s;
        }
        @keyframes fadein {
            from {bottom: 0; opacity: 0;}
            to {bottom: 30px; opacity: 1;}
        }
        @keyframes fadeout {
            from {bottom: 30px; opacity: 1;}
            to {bottom: 0; opacity: 0;}
        }
    </style>
</head>
<body>
    <button id="showToastBtn">Show Toast</button>
    <div id="toast" class="toast">This is a toast notification!</div>

    <script>
        const showToastBtn = document.getElementById('showToastBtn');
        const toast = document.getElementById('toast');

        showToastBtn
.addEventListener('click', () => {
            toast.className = 'toast show';
            setTimeout(() => {
                toast.className = toast.className.replace('show', '');
            }, 3000); // Toast will disappear after 3 seconds
        });
    </script>
</body>
</html>
```

## Debounced Search
Debounced search is a technique used to limit the number of times a search function is called while the user is typing. It helps improve performance and reduce unnecessary API calls by waiting for a specified amount of time after the user stops typing before executing the search function. JavaScript can be used to implement debounced search by using timers and event listeners.

### Example of Debounced Search
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Debounced Search Example</title>
    <style>
        .result {
            margin: 5px 0;
        }
    </style>
</head>
<body>
    <input type="text" id="searchInput" placeholder="Search...">
    <div id="results"></div>

    <script>
        const data = [
            'Apple',
            'Banana',
            'Cherry',
            'Date',
            'Elderberry',
            'Fig',
            'Grape',
            'Honeydew'
        ];

        const searchInput = document.getElementById('searchInput');
        const resultsDiv = document.getElementById('results');
        let debounceTimer;

        searchInput.addEventListener('input', () => {
            clearTimeout(debounceTimer);
            debounceTimer = setTimeout(() => {
                const query = searchInput.value.toLowerCase();
                resultsDiv.innerHTML = '';

                const filteredResults = data.filter(item => item.toLowerCase().includes(query));

                if (filteredResults.length > 0) {
                    filteredResults.forEach(item => {
                        const resultItem = document.createElement('div');
                        resultItem.className = 'result';
                        resultItem.textContent = item;
                        resultsDiv.appendChild(resultItem);
                    });
                } else {
                    resultsDiv.textContent = 'No results found.';
                }
            }, 300); // Wait for 300ms after the user stops typing
        });
    </script>
</body>
</html>
```

## Throttled Scrolling
Throttled scrolling is a technique used to limit the number of times a scroll event handler is executed while the user is scrolling. It helps improve performance by reducing the frequency of function calls, especially when dealing with heavy computations or DOM manipulations. JavaScript can be used to implement throttled scrolling by using timers and event listeners.

### Example of Throttled Scrolling
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Throttled Scrolling Example</title>
    <style>
        .item {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <div id="contentContainer"></div>

    <script>
        const contentContainer = document.getElementById('contentContainer');
        let itemCount = 0;
        const itemsPerLoad = 20;
        let isThrottled = false;

        function loadMoreItems() {
            for (let i = 0; i < itemsPerLoad; i++) {
                itemCount++;
                const itemDiv = document.createElement('div');
                itemDiv.className = 'item';
                itemDiv.textContent = `Item ${itemCount}`;
                contentContainer.appendChild(itemDiv);
            }
        }

        window.addEventListener('scroll', () => {
            if (!isThrottled) {
                isThrottled = true;
                setTimeout(() => {
                    if (window.innerHeight + window.scrollY >= document.body.offsetHeight - 100) {
                        loadMoreItems();
                    }
                    isThrottled = false;
                }, 200); // Throttle the scroll event to fire every 200ms
            }
        });

        // Initial load
        loadMoreItems();
    </script>
</body>
</html>
```

## API integration
API integration is the process of connecting a web application to external services or data sources through APIs (Application Programming Interfaces). It allows developers to fetch, send, and manipulate data from third-party services, enabling features such as user authentication, data retrieval, and interaction with external platforms. JavaScript can be used to make API requests using methods like `fetch` or libraries like Axios.

### Example of API Integration
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>API Integration Example</title>
    <style>
        .user {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <button id="loadUsersBtn">Load Users</button>
    <div id="usersContainer"></div>

    <script>
        const loadUsersBtn = document.getElementById('loadUsersBtn');
        const usersContainer = document.getElementById('usersContainer');

        loadUsersBtn.addEventListener('click', () => {
            fetch('https://jsonplaceholder.typicode.com/users')
                .then(response => response.json())
                .then(users => {
                    usersContainer.innerHTML = '';
                    users.forEach(user => {
                        const userDiv = document.createElement('div');
                        userDiv.className = 'user';
                        userDiv.innerHTML = `<strong>${user.name}</strong><br>Email: ${user.email}<br>Phone: ${user.phone}`;
                        usersContainer.appendChild(userDiv);
                    });
                })
                .catch(error => {
                    usersContainer.textContent = 'Error loading users.';
                    console.error(error);
                });
        });
    </script>
</body>
</html>
```

## Authentication flow
Authentication flow is the process of verifying the identity of a user before granting access to a web application or specific resources. It typically involves steps such as user registration, login, token generation, and session management. JavaScript can be used to handle authentication flow by interacting with backend APIs, managing tokens, and controlling access to protected routes.

### Example of Authentication Flow
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Authentication Flow Example</title>
    <style>
        .hidden {
            display: none;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>
    <div id="loginForm">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username"><br><br>
        <input type="password" id="password" placeholder="Password"><br><br>
        <button id="loginBtn">Login</button>
        <div id="loginError" class="error"></div>
    </div>

    <div id="welcomeMessage" class="hidden">
        <h2>Welcome, <span id="userDisplay"></span>!</h2>
        <button id="logoutBtn">Logout</button>
    </div>

    <script>
        const loginForm = document.getElementById('loginForm');
        const welcomeMessage = document.getElementById('welcomeMessage');
        const userDisplay = document.getElementById('userDisplay');
        const loginError = document.getElementById('loginError');

        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');

        loginBtn.addEventListener('click', () => {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Simulate authentication (replace with actual API call)
            if (username === 'user' && password === 'pass') {
                localStorage.setItem('authToken', 'dummyToken'); // Store token
                userDisplay.textContent = username;
                loginForm.classList.add('hidden');
                welcomeMessage.classList.remove('hidden');
                loginError.textContent = '';
            } else {
                loginError.textContent = 'Invalid username or password.';
            }
        });

        logoutBtn.addEventListener('click', () => {
            localStorage.removeItem('authToken'); // Remove token
            loginForm.classList.remove('hidden');
            welcomeMessage.classList.add('hidden');
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        });

        // Check for existing token on page load
        window.addEventListener('load', () => {
            const token = localStorage.getItem('authToken');
            if (token) {
                userDisplay.textContent = 'user'; // Replace with actual username retrieval
                loginForm.classList.add('hidden');
                welcomeMessage.classList.remove('hidden');
            }
        });
    </script>
</body>
</html>
```

## Protected routes
Protected routes are sections of a web application that require user authentication to access. They ensure that only authorized users can view or interact with certain pages or features. JavaScript can be used to implement protected routes by checking for authentication tokens or user roles before rendering the content, and redirecting unauthorized users to a login page or an error message.

### Example of Protected Routes
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Protected Routes Example</title>
    <style>
        .hidden {
            display: none;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>
    <div id="loginForm">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username"><br><br>
        <input type="password" id="password" placeholder="Password"><br><br>
        <button id="loginBtn">Login</button>
        <div id="loginError" class="error"></div>
    </div>

    <div id="protectedContent" class="hidden">
        <h2>Protected Content</h2>
        <p>This content is only visible to authenticated users.</p>
        <button id="logoutBtn">Logout</button>
    </div>

    <script>
        const loginForm = document.getElementById('loginForm');
        const protectedContent = document.getElementById('protectedContent');
        const loginError = document.getElementById('loginError');

        const loginBtn = document.getElementById('loginBtn');
        const logoutBtn = document.getElementById('logoutBtn');

        loginBtn.addEventListener('click', () => {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Simulate authentication (replace with actual API call)
            if (username === 'user' && password === 'pass') {
                localStorage.setItem('authToken', 'dummyToken'); // Store token
                loginForm.classList.add('hidden');
                protectedContent.classList.remove('hidden');
                loginError.textContent = '';
            } else {
                loginError.textContent = 'Invalid username or password.';
            }
        });

        logoutBtn.addEventListener('click', () => {
            localStorage.removeItem('authToken'); // Remove token
            loginForm.classList.remove('hidden');
            protectedContent.classList.add('hidden');
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        });

        // Check for existing token on page load
        window.addEventListener('load', () => {
            const token = localStorage.getItem('authToken');
            if (token) {
                loginForm.classList.add('hidden');
                protectedContent.classList.remove('hidden');
            }
        });
    </script>
</body>
</html>
```

## Error states
Error states are conditions in a web application that indicate something has gone wrong, such as failed API requests, form validation errors, or unexpected behavior. Handling error states effectively is crucial for providing a good user experience. JavaScript can be used to detect errors, display appropriate messages, and guide users on how to resolve issues.

### Example of Error States
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Error States Example</title>
    <style>
        .error {
            color: red;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <button id="fetchDataBtn">Fetch Data</button>
    <div id="errorMessage" class="error"></div>

    <script>
        const fetchDataBtn = document.getElementById('fetchDataBtn');
        const errorMessage = document.getElementById('errorMessage');

        fetchDataBtn.addEventListener('click', () => {
            // Simulate an API request (replace with actual API call)
            fetch('https://jsonplaceholder.typicode.com/invalid-endpoint')
                .then(response => {
                    if (!response.ok) {
                        throw new Error('Network response was not ok');
                    }
                    return response.json();
                })
                .then(data => {
                    errorMessage.textContent = '';
                    console.log(data);
                })
                .catch(error => {
                    errorMessage.textContent = 'Error fetching data: ' + error.message;
                    console.error(error);
                });
        });
    </script>
</body>
</html>
```

## Loading States
Loading states are visual indicators that inform users that a process is ongoing, such as data fetching, form submission, or page loading. They help manage user expectations and improve the overall user experience by providing feedback during potentially long-running operations. JavaScript can be used to implement loading states by toggling visibility of loading indicators and managing the state of interactive elements.

### Example of Loading States
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loading States Example</title>
    <style>
        .loading {
            display: none;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <button id="loadDataBtn">Load Data</button>
    <div id="loadingIndicator" class="loading">Loading...</div>
    <div id="dataContainer"></div>

    <script>
        const loadDataBtn = document.getElementById('loadDataBtn');
        const loadingIndicator = document.getElementById('loadingIndicator');
        const dataContainer = document.getElementById('dataContainer');

        loadDataBtn.addEventListener('click', () => {
            loadingIndicator.style.display = 'block';
            dataContainer.textContent = '';

            // Simulate an API request (replace with actual API call)
            setTimeout(() => {
                loadingIndicator.style.display = 'none';
                dataContainer.textContent = 'Data loaded successfully!';
            }, 2000); // Simulate a 2-second delay
        });
    </script>
</body>
</html>
```

## Optimistic UI
Optimistic UI is a user interface design pattern that provides immediate feedback to users by updating the UI before receiving confirmation from the server. This approach enhances the user experience by making the application feel faster and more responsive. JavaScript can be used to implement optimistic UI by temporarily updating the UI and then handling success or failure responses from the server.

### Example of Optimistic UI
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Optimistic UI Example</title>
    <style>
        .item {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>
    <div id="itemsContainer"></div>
    <button id="addItemBtn">Add Item</button>
    <div id="errorMessage" class="error"></div>

    <script>
        const itemsContainer = document.getElementById('itemsContainer');
        const addItemBtn = document.getElementById('addItemBtn');
        const errorMessage = document.getElementById('errorMessage');

        let itemCount = 0;

        addItemBtn.addEventListener('click', () => {
            itemCount++;
            const newItem = document.createElement('div');
            newItem.className = 'item';
            newItem.textContent = `Item ${itemCount} (Pending...)`;
            itemsContainer.appendChild(newItem);

            // Simulate an API request (replace with actual API call)
            setTimeout(() => {
                // Simulate success or failure
                const isSuccess = Math.random() > 0.2; // 80% chance of success
                if (isSuccess) {
                    newItem.textContent = `Item ${itemCount} (Confirmed)`;
                    errorMessage.textContent = '';
                } else {
                    itemsContainer.removeChild(newItem);
                    errorMessage.textContent = 'Error adding item. Please try again.';
                }
            }, 1000); // Simulate a 1-second delay
        });
    </script>
</body>
</html>
```

## Caching
Caching is a technique used to store frequently accessed data in a temporary storage location, allowing for faster retrieval and improved performance. In web applications, caching can be implemented on the client-side (e.g., using localStorage or sessionStorage) or server-side (e.g., using caching headers or a caching layer). JavaScript can be used to manage client-side caching by storing and retrieving data from localStorage or sessionStorage.

### Example of Caching
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Caching Example</title>
    <style>
        .item {
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <button id="loadDataBtn">Load Data</button>
    <div id="dataContainer"></div>

    <script>
        const loadDataBtn = document.getElementById('loadDataBtn');
        const dataContainer = document.getElementById('dataContainer');

        loadDataBtn.addEventListener('click', () => {
            // Check if data is already cached
            const cachedData = localStorage.getItem('cachedItems');
            if (cachedData) {
                displayData(JSON.parse(cachedData));
            } else {
                // Simulate an API request (replace with actual API call)
                setTimeout(() => {
                    const data = [
                        'Item 1',
                        'Item 2',
                        'Item 3',
                        'Item 4',
                        'Item 5'
                    ];
                    localStorage.setItem('cachedItems', JSON.stringify(data)); // Cache the data
                    displayData(data);
                }, 1000); // Simulate a 1-second delay
            }
        });

        function displayData(data) {
            dataContainer.innerHTML = '';
            data.forEach(item => {
                const itemDiv = document.createElement('div');
                itemDiv.className = 'item';
                itemDiv.textContent = item;
                dataContainer.appendChild(itemDiv);
            });
        }
    </script>
</body>
</html>
```

## Offline handling
Offline handling is the process of managing the behavior of a web application when the user loses internet connectivity. It involves detecting the online/offline status, providing feedback to users, and ensuring that the application can still function or gracefully degrade when offline. JavaScript can be used to implement offline handling by listening for online and offline events and managing cached data.

### Example of Offline Handling
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Offline Handling Example</title>
    <style>
        .status {
            margin-top: 10px;
            font-weight: bold;
        }
        .offline {
            color: red;
        }
        .online {
            color: green;
        }
    </style>
</head>
<body>
    <div id="status" class="status">Checking connection...</div>

    <script>
        const statusDiv = document.getElementById('status');

        function updateStatus() {
            if (navigator.onLine) {
                statusDiv.textContent = 'You are online.';
                statusDiv.className = 'status online';
            } else {
                statusDiv.textContent = 'You are offline. Some features may not be available.';
                statusDiv.className = 'status offline';
            }
        }

        window.addEventListener('online', updateStatus);
        window.addEventListener('offline', updateStatus);

        // Initial check
        updateStatus();
    </script>
</body>
</html>
```

                       