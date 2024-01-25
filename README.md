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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)

#### 2. Web Storage API
```javascript
// Store Data
localStorage.setItem('key', 'value');

// Retrieve Data
const storedValue = localStorage.getItem('key');

// Remove Data
localStorage.removeItem('key');
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)

#### 3. Web Fetch API
```javascript
fetch('http://example.com/movies.json')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('error:', error));
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

#### 6. Web Audio API
```javascript
const audioContext = new (window.AudioContext || window.webkitAudioContext)();
const oscillator = audioContext.createOscillator();

oscillator.frequency.setValueAtTime(440, audioContext.currentTime);
oscillator.connect(audioContext.destination);
oscillator.start();
oscillator.stop(audioContext.currentTime + 1);
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)

#### 7. Web Sockets API
```javascript
const socket = new WebSocket('wss://example.com/socket');

socket.addEventListener('open', () => socket.send('Hello, server!'));
socket.addEventListener('message', event => console.log('Received: ', event.data));
socket.addEventListener('close', () => console.log('Connection closed.'));
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/File_API)

#### 10. Web Notification API
```javascript
Notification.requestPermission()
  .then( permission => {
    new Notification('Hello, World!');
  });
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)

#### 11. Web Workers API
```javascript
const worker = new Worker('worker.js');
worker.postMessage('Hello from main script!');
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)

#### 12. Web Intersection Observer API
```javascript
const observer = new IntersectionObserver(entries => entries.forEach( entry => entry.isIntersecting && console.log('Element is in the viewport!') ) );
observer.observe(document.getElementById('yourElementId'));
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver)

#### 14. Web Pointer Lock API
```javascript
const element = document.getElementById('yourElementId');
element.requestPointerLock();
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API)

#### 15. Web Battery Status API
```javascript
navigator.getBattery().then(battery => {
  console.log('Battery Level:', battery.level * 100 + '%');
  console.log('Charging:', battery.charging ? 'Yes' : 'No');
});
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Battery_Status_API)

#### 16. Web Gamepad API
```javascript
window.addEventListener("gamepadconnected", (event) => 
  console.log("Gamepad connected:", event.gamepad.id)
);

window.addEventListener("gamepaddisconnected", (event) => 
  console.log("Gamepad disconnected:", event.gamepad.id)
);
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API)

#### 17. Web Device Orientation and Motion API
```javascript
window.addEventListener("deviceorientation", (event) => {
  console.log("Device Orientation:", event.alpha, event.beta, event.gamma);
});

window.addEventListener("devicemotion", (event) => {
  console.log("Device Motion:", event.acceleration.x, event.acceleration.y, event.acceleration.z);
});
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Device_orientation_events)

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
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Push_API)

#### 19. Web Payment Request API
```javascript
const supportedInstruments = [{ supportedMethods: 'basic-card' }];
const paymentDetails = { total: { label: 'Total', amount: { currency: 'USD', value: '10.00' } } };
const paymentPromise = new PaymentRequest(supportedInstruments, paymentDetails);

paymentPromise.show().then(paymentResponse =>
  paymentResponse.complete('success')
);
```
[MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API)

<hr>




## UI/UX Design

#### Figma

- [Figma Web](https://www.figma.com)
- [Figma App](https://desktop.figma.com/win/FigmaSetup.exe)

Mockups
- [Mockup](https://www.figma.com/community/plugin/817043359134136295)
- [Mockuuups Studio](https://www.figma.com/community/plugin/786250770157843670)
- [Artboard Studio Mockups](https://www.figma.com/community/plugin/750673765607708804)
- [Angle Mockups](https://www.figma.com/community/plugin/778645840235495725)
- [MockRocket – 3D Mockups](https://www.figma.com/community/plugin/1051242643585430631)
- [Clay Mockups 3D](https://www.figma.com/community/plugin/819335598581469537)
- [Rotato 3D Mockups + Explosions](https://www.figma.com/community/plugin/1009741687635558607)
- [Easy Mockup](https://www.figma.com/community/plugin/1180592708021765520)
- [A Little Bit Mockup](https://www.figma.com/community/plugin/1149987037748021167)

Others
- [Avatars](https://www.figma.com/community/plugin/739659977030056719)
- [EOS Icons](https://www.figma.com/community/plugin/1131638845835688020)
- [Export Images](https://www.figma.com/community/plugin/1073791321657719341)
- [Mesh Gradient](https://www.figma.com/community/plugin/958202093377483021)
- [Simple Icons](https://www.figma.com/community/plugin/1149614463603005908)
- [LottieFiles](https://www.figma.com/community/plugin/809860933081065308)

<hr>




## APIs
- https://github.com/marcelscruz/public-apis
- https://www.jsonapi.co/public-api
- https://any-api.com

<hr>




## GitHub Student Developer Pack
- https://education.github.com/pack

<hr>




## Visual Studio

[Download Visual Studio Code](https://code.visualstudio.com)

Extensions
- [Alphabetical Sorter](https://marketplace.visualstudio.com/items?itemName=ue.alphabetical-sorter)
- [Atom Material Icons](https://marketplace.visualstudio.com/items?itemName=AtomMaterial.a-file-icon-vscode)
- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Auto Complete Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-complete-tag)
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info)
- [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
- [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [HTML Boilerplate](https://marketplace.visualstudio.com/items?itemName=sidthesloth.html5-boilerplate)
- [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
- [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Lorem Ipsum](https://marketplace.visualstudio.com/items?itemName=Tyriar.lorem-ipsum)
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Theme](https://marketplace.visualstudio.com/items?itemName=tal7aouy.theme)
- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

<hr>




## Learning Resources
- https://github.com/tiimgreen/github-cheat-sheet
- https://github.com/microsoft/Web-Dev-For-Beginners
- https://github.com/florinpop17/app-ideas
- https://github.com/thedaviddias/Front-End-Checklist
- https://github.com/marcobiedermann/search-engine-optimization
- https://github.com/levinunnink/html-form-to-google-sheet
- https://github.com/freeCodeCamp/freeCodeCamp
- https://github.com/joshbuchea/HEAD
- https://github.com/phuocng/html-dom
- https://www.w3schools.com/html/default.asp
- https://www.w3schools.com/css/default.asp
- https://www.w3schools.com/js/default.asp
- https://www.geeksforgeeks.org/html-cheat-sheet-a-basic-guide-to-html
- https://www.geeksforgeeks.org/css-cheat-sheet-a-basic-guide-to-css
- https://www.geeksforgeeks.org/javascript-cheat-sheet-a-basic-guide-to-javascript
- https://www.freecodecamp.org/news/search/?query=html
- https://www.freecodecamp.org/news/tag/html
- https://www.freecodecamp.org/news/tag/html5
- https://www.freecodecamp.org/news/search/?query=css
- https://www.freecodecamp.org/news/tag/css
- https://www.freecodecamp.org/news/search/?query=javascript
- https://www.freecodecamp.org/news/tag/javascript

<hr>




### Frameworks / Toolkits:
- https://github.com/tailwindlabs/tailwindcss
- https://github.com/twbs/bootstrap
- https://github.com/FortAwesome/Font-Awesome
- https://github.com/simple-icons/simple-icons
- https://github.com/supabase/supabase

<hr>




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
