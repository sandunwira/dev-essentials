# dev-essentials
Contains resources for startup projects

<hr>

## Git and GitHub

#### 1. `git config`
Sets the username and email address for commits.
```
git config --global user.name "Your Name"
git config --global user.email "youremail@mail.com"
```

#### 2. `git init`
Initialize repository as git repository.
```
git init
```

#### 3. `git clone [url]`
Clones repository from a server like GitHub, GitLab etc.
```
git clone https://github.com/username/repository.git
```

#### 4. `git status`
Checks the current status of working tree.
```
git status
```

#### 5. `git add [Filename(s)]`
Puts the unstage files to staging area.
```
// Add Specific Files
git add index.html style.css script.js

// Add Everything
git add .
```

#### 6. `git commit -m [Message]`
Records changes to the git repo by saving a log together with a commit ID
```
git commit -m "fixed bug"
// Commit all files without a commit message
git commit -a
```

#### 7. `git remote [options] [variable] [url]`
Connects your local repository to the remote repository over a server.
```
git remote add origin https://github.com/username/repository.git
```

<hr>




## JavaScript Web APIs

#### 1. Web Speech API
```javascript
const textToSpeak = "Hello There";
const utterance = new SpeechSynthesisUtterance(textToSpeak);

window.speechSynthesis.speak(utterance);
```

#### 2. Web Storage API
```javascript
// Store Data
localStorage.setItem('key', 'value');

// Retrieve Data
const storedValue = localStorage.getItem('key');

// Remove Data
localStorage.removeItem('key');
```

#### 3. Web Fetch API
```javascript
fetch('http://example.com/movies.json')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('error:', error));
```

#### 4. Web Geolocation API
```javascript
navigator.geolocation.getCurrentPosition(
  position => {
    console.log(`Latitude: ${position.coords.latitude}, Longitude: ${position.coords.longitude}`);
  },
  error => {
    console.error("Error getting location:", error.message);
  }
);
```

#### 5. Web Canvas API
```javascript
const canvas = document.createElement('canvas');
canvas.width = 200;
canvas.height = 100;
document.body.appendChild(canvas);

const ctx = canvas.getContext('2d');
ctx.fillStyle = 'blue';
ctx.fillRect(10, 10, 180, 80);
```

#### 6. Web Audio API
```javascript
const audioContext = new (window.AudioContext || window.webkitAudioContext)();
const oscillator = audioContext.createOscillator();

oscillator.frequency.setValueAtTime(440, audioContext.currentTime);
oscillator.connect(audioContext.destination);
oscillator.start();
oscillator.stop(audioContext.currentTime + 1);
```

#### 7. Web Sockets API
```javascript
const socket = new WebSocket('wss://example.com/socket');

socket.addEventListener('open', () => socket.send('Hello, server!'));
socket.addEventListener('message', event => console.log('Received: ', event.data));
socket.addEventListener('close', () => console.log('Connection closed.'));
```

#### 8. Web IndexedDB API
```javascript
// Open (or create) the database
const dbName = "InstagramPostsDB";
const dbVersion = 1;

const request = indexedDB.open(dbName, dbVersion);

// handles errors that may occur during the database opening process.
request.onerror(() => {});
// specifies the actions to be taken when the database structure is being upgraded.
request.onupgradeneeded(() => {});
// defines the actions to be taken upon successful opening of the database.
request.onsuccess(() => {});
```

#### 9. Web File API
```javascript
<input type="file" id="imageInput" accept="image/*">
<button onclick="uploadPost()">Upload Post</button>

<script>
  function uploadPost() {
    const file = document.getElementById('imageInput').files[0];
    console.log('Selected file:', file);
  }
</script>
```

#### 10. Web Notification API
```javascript
Notification.requestPermission()
  .then( permission => {
    new Notification('Hello, World!');
  });
```

#### 11. Web Workers API
```javascript
const worker = new Worker('worker.js');
worker.postMessage('Hello from main script!');
```

#### 12. Web Intersection Observer API
```javascript
const observer = new IntersectionObserver(entries => entries.forEach( entry => entry.isIntersecting && console.log('Element is in the viewport!') ) );
observer.observe(document.getElementById('yourElementId'));
```

#### 13. Web Mutation Observer API
```javascript
const observer = new MutationObserver(mutations =>
  mutations.forEach(mutation =>
    console.log('DOM change detected:', mutation)
  )
);
const targetNode = document.getElementById('yourElementId');
const config = { attributes: true, childList: true, subtree: true };

observer.observe(targetNode, config); // Start observing DOM changes.
```

#### 14. Web Pointer Lock API
```javascript
const element = document.getElementById('yourElementId');
element.requestPointerLock();
```

#### 15. Web Battery Status API
```javascript
navigator.getBattery().then(battery => {
  console.log('Battery Level:', battery.level * 100 + '%');
  console.log('Charging:', battery.charging ? 'Yes' : 'No');
});
```

#### 16. Web Gamepad API
```javascript
window.addEventListener("gamepadconnected", (event) => 
  console.log("Gamepad connected:", event.gamepad.id)
);

window.addEventListener("gamepaddisconnected", (event) => 
  console.log("Gamepad disconnected:", event.gamepad.id)
);

```

#### 17. Web Device Orientation and Motion API
```javascript
window.addEventListener("deviceorientation", (event) => {
  console.log("Device Orientation:", event.alpha, event.beta, event.gamma);
});

window.addEventListener("devicemotion", (event) => {
  console.log("Device Motion:", event.acceleration.x, event.acceleration.y, event.acceleration.z);
});
```

#### 18. Web Push API
```javascript
// Check for Push API support
if ('PushManager' in window) {
  // Request notification permission
  Notification.requestPermission().then(permission => {
    if (permission === 'granted') {
      // Subscription logic goes here
    }
  });
}
```

#### 19. Web Payment Request API
```javascript
const supportedInstruments = [{ supportedMethods: 'basic-card' }];
const paymentDetails = { total: { label: 'Total', amount: { currency: 'USD', value: '10.00' } } };
const paymentPromise = new PaymentRequest(supportedInstruments, paymentDetails);

paymentPromise.show().then(paymentResponse =>
  paymentResponse.complete('success')
);
```

<hr>




## UI/UX Design

#### Figma

Mockups
- https://www.figma.com/community/plugin/817043359134136295/mockup
- https://www.figma.com/community/plugin/786250770157843670/mockuuups-studio
- https://www.figma.com/community/plugin/750673765607708804/artboard-studio-mockups
- https://www.figma.com/community/plugin/778645840235495725/angle-mockups
- https://www.figma.com/community/plugin/1051242643585430631/mockrocket-3d-mockups
- https://www.figma.com/community/plugin/819335598581469537/clay-mockups-3d
- https://www.figma.com/community/plugin/1009741687635558607/rotato-3d-mockups-explosions
- https://www.figma.com/community/plugin/1180592708021765520/easy-mockup



<hr>




### Public APIs:
- https://github.com/marcelscruz/public-apis
- https://www.jsonapi.co/public-api
- https://any-api.com

### Useful Links:
- https://github.com/tiimgreen/github-cheat-sheet
- https://github.com/microsoft/Web-Dev-For-Beginners
- https://github.com/florinpop17/app-ideas
- https://github.com/thedaviddias/Front-End-Checklist
- https://github.com/marcobiedermann/search-engine-optimization
- https://github.com/freeCodeCamp/freeCodeCamp
- https://github.com/joshbuchea/HEAD
- https://github.com/phuocng/html-dom
- https://www.w3schools.com/html/default.asp
- https://www.w3schools.com/css/default.asp
- https://www.w3schools.com/js/default.asp
- https://www.geeksforgeeks.org/html-cheat-sheet-a-basic-guide-to-html
- https://www.geeksforgeeks.org/css-cheat-sheet-a-basic-guide-to-css
- https://www.geeksforgeeks.org/javascript-cheat-sheet-a-basic-guide-to-javascript
- https://education.github.com/pack

### Useful Repos:
- https://github.com/levinunnink/html-form-to-google-sheet

### Frameworks / Toolkits:
- https://github.com/tailwindlabs/tailwindcss
- https://github.com/twbs/bootstrap
- https://github.com/FortAwesome/Font-Awesome
- https://github.com/simple-icons/simple-icons
- https://github.com/supabase/supabase

### Projects:
- Portfolio (Live using GitHub Pages)
- To-do List / Note-taking Website
- Product / Event / Business Landing page
- Blog Website
- Weather Website (Work with APIs)
- Interactive Quiz (Work with APIs)
- Currency or Unit Converter (Work with APIs)
- Music Player (Local files or Work with APIs)
- News Reader (Work with APIs)
- Simple Games (Example: Rock, Paper, Scissors)
- Movie Finder (Work with APIs)
- Book Finder (Work with APIs)
- Task Planner
- Random Quote Generator (Work with APIs)
- Simple Calculator
- Interactive Drawing Canvas
- Digital Clock
- BMI Calculator
- Event Countdown Timer
- Random HEX Color Code Generator (with Preview)
- Simple Firefox / Chrome Extensions
