<div align="center">
  <h2>Dev Essentials</h2>
  <p>Essentials when developing websites and apps</p>
</div>




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

- [x] [Figma Web](https://www.figma.com)
- [x] [Figma App](https://desktop.figma.com/win/FigmaSetup.exe)

Mockups
- [x] [Mockup](https://www.figma.com/community/plugin/817043359134136295)
- [x] [Mockuuups Studio](https://www.figma.com/community/plugin/786250770157843670)
- [x] [Artboard Studio Mockups](https://www.figma.com/community/plugin/750673765607708804)
- [x] [Angle Mockups](https://www.figma.com/community/plugin/778645840235495725)
- [x] [MockRocket – 3D Mockups](https://www.figma.com/community/plugin/1051242643585430631)
- [x] [Clay Mockups 3D](https://www.figma.com/community/plugin/819335598581469537)
- [x] [Rotato 3D Mockups + Explosions](https://www.figma.com/community/plugin/1009741687635558607)
- [x] [Easy Mockup](https://www.figma.com/community/plugin/1180592708021765520)
- [x] [A Little Bit Mockup](https://www.figma.com/community/plugin/1149987037748021167)

Others
- [x] [Avatars](https://www.figma.com/community/plugin/739659977030056719)
- [x] [EOS Icons](https://www.figma.com/community/plugin/1131638845835688020)
- [x] [Export Images](https://www.figma.com/community/plugin/1073791321657719341)
- [x] [Mesh Gradient](https://www.figma.com/community/plugin/958202093377483021)
- [x] [Simple Icons](https://www.figma.com/community/plugin/1149614463603005908)
- [x] [LottieFiles](https://www.figma.com/community/plugin/809860933081065308)

<hr>




## APIs
- [x] https://github.com/marcelscruz/public-apis
- [x] https://www.jsonapi.co/public-api
- [x] https://any-api.com

<hr>




## GitHub Student Developer Pack
- [x] https://education.github.com/pack

<hr>




## Visual Studio

- [x] [Download Visual Studio Code](https://code.visualstudio.com)

Extensions
- [x] [Alphabetical Sorter](https://marketplace.visualstudio.com/items?itemName=ue.alphabetical-sorter)
- [x] [Atom Material Icons](https://marketplace.visualstudio.com/items?itemName=AtomMaterial.a-file-icon-vscode)
- [x] [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [x] [Auto Complete Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-complete-tag)
- [x] [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [x] [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info)
- [x] [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
- [x] [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [x] [HTML Boilerplate](https://marketplace.visualstudio.com/items?itemName=sidthesloth.html5-boilerplate)
- [x] [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
- [x] [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow)
- [x] [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [x] [Lorem Ipsum](https://marketplace.visualstudio.com/items?itemName=Tyriar.lorem-ipsum)
- [x] [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
- [x] [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
- [x] [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [x] [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [x] [Theme](https://marketplace.visualstudio.com/items?itemName=tal7aouy.theme)
- [x] [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

<hr>




## Learning Resources
- [x] https://github.com/tiimgreen/github-cheat-sheet
- [x] https://github.com/microsoft/Web-Dev-For-Beginners
- [x] https://github.com/florinpop17/app-ideas
- [x] https://github.com/thedaviddias/Front-End-Checklist
- [x] https://github.com/marcobiedermann/search-engine-optimization
- [x] https://github.com/levinunnink/html-form-to-google-sheet
- [x] https://github.com/freeCodeCamp/freeCodeCamp
- [x] https://github.com/joshbuchea/HEAD
- [x] https://github.com/phuocng/html-dom
- [x] https://www.w3schools.com/html/default.asp
- [x] https://www.w3schools.com/css/default.asp
- [x] https://www.w3schools.com/js/default.asp
- [x] https://www.geeksforgeeks.org/html-cheat-sheet-a-basic-guide-to-html
- [x] https://www.geeksforgeeks.org/css-cheat-sheet-a-basic-guide-to-css
- [x] https://www.geeksforgeeks.org/javascript-cheat-sheet-a-basic-guide-to-javascript
- [x] https://www.freecodecamp.org/news/search/?query=html
- [x] https://www.freecodecamp.org/news/tag/html
- [x] https://www.freecodecamp.org/news/tag/html5
- [x] https://www.freecodecamp.org/news/search/?query=css
- [x] https://www.freecodecamp.org/news/tag/css
- [x] https://www.freecodecamp.org/news/search/?query=javascript
- [x] https://www.freecodecamp.org/news/tag/javascript

<hr>




### Frameworks / Toolkits:
- [x] https://github.com/tailwindlabs/tailwindcss
- [x] https://github.com/twbs/bootstrap
- [x] https://github.com/FortAwesome/Font-Awesome
- [x] https://github.com/simple-icons/simple-icons
- [x] https://github.com/supabase/supabase

<hr>




### Projects:
- [x] Portfolio (Live using GitHub Pages)
- [x] To-do List / Note-taking Website
- [x] Product / Event / Business Landing page
- [x] Blog Website
- [x] Weather Website (Work with APIs)
- [x] Interactive Quiz (Work with APIs)
- [x] Currency or Unit Converter (Work with APIs)
- [x] Music Player (Local files or Work with APIs)
- [x] News Reader (Work with APIs)
- [x] Simple Games (Example: Rock, Paper, Scissors)
- [x] Movie Finder (Work with APIs)
- [x] Book Finder (Work with APIs)
- [x] Task Planner
- [x] Random Quote Generator (Work with APIs)
- [x] Simple Calculator
- [x] Interactive Drawing Canvas
- [x] Digital Clock
- [x] BMI Calculator
- [x] Event Countdown Timer
- [x] Random HEX Color Code Generator (with Preview)
- [x] Simple Firefox / Chrome Extensions
