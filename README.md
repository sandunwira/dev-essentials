<div align="center">
  <h2>Dev Essentials</h2>
  <p>Essentials when developing websites and apps</p>
</div>




### JavaScript Web APIs:

##### 1. [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API):
```javascript
const textToSpeak = "Hello There";
const utterance = new SpeechSynthesisUtterance(textToSpeak);

window.speechSynthesis.speak(utterance);
```

##### 2. [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API):
```javascript
// Store Data
localStorage.setItem('key', 'value');

// Retrieve Data
const storedValue = localStorage.getItem('key');

// Remove Data
localStorage.removeItem('key');
```

##### 3. [Web Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API):
```javascript
fetch('http://example.com/movies.json')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('error:', error));
```

##### 4. [Web Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API):
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

##### 5. [Web Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API):
```javascript
const canvas = document.createElement('canvas');
canvas.width = 200;
canvas.height = 100;
document.body.appendChild(canvas);

const ctx = canvas.getContext('2d');
ctx.fillStyle = 'blue';
ctx.fillRect(10, 10, 180, 80);
```

##### 6. [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API):
```javascript
const audioContext = new (window.AudioContext || window.webkitAudioContext)();
const oscillator = audioContext.createOscillator();

oscillator.frequency.setValueAtTime(440, audioContext.currentTime);
oscillator.connect(audioContext.destination);
oscillator.start();
oscillator.stop(audioContext.currentTime + 1);
```

##### 7. [Web Sockets API](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket):
```javascript
const socket = new WebSocket('wss://example.com/socket');

socket.addEventListener('open', () => socket.send('Hello, server!'));
socket.addEventListener('message', event => console.log('Received: ', event.data));
socket.addEventListener('close', () => console.log('Connection closed.'));
```

##### 8. [Web IndexedDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API):
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

##### 9. [Web File API](https://developer.mozilla.org/en-US/docs/Web/API/File_API):
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

##### 10. [Web Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API):
```javascript
Notification.requestPermission()
  .then( permission => {
    new Notification('Hello, World!');
  });
```

##### 11. [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API):
```javascript
const worker = new Worker('worker.js');
worker.postMessage('Hello from main script!');
```

##### 12. [Web Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API):
```javascript
const observer = new IntersectionObserver(entries => entries.forEach( entry => entry.isIntersecting && console.log('Element is in the viewport!') ) );
observer.observe(document.getElementById('yourElementId'));
```

##### 13. [Web Mutation Observer API](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver):
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

##### 14. [Web Pointer Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API):
```javascript
const element = document.getElementById('yourElementId');
element.requestPointerLock();
```

##### 15. [Web Battery Status API](https://developer.mozilla.org/en-US/docs/Web/API/Battery_Status_API):
```javascript
navigator.getBattery().then(battery => {
  console.log('Battery Level:', battery.level * 100 + '%');
  console.log('Charging:', battery.charging ? 'Yes' : 'No');
});
```

##### 16. [Web Gamepad API](https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API):
```javascript
window.addEventListener("gamepadconnected", (event) => 
  console.log("Gamepad connected:", event.gamepad.id)
);

window.addEventListener("gamepaddisconnected", (event) => 
  console.log("Gamepad disconnected:", event.gamepad.id)
);
```

##### 17. [Web Device Orientation and Motion API](https://developer.mozilla.org/en-US/docs/Web/API/Device_orientation_events):
```javascript
window.addEventListener("deviceorientation", (event) => {
  console.log("Device Orientation:", event.alpha, event.beta, event.gamma);
});

window.addEventListener("devicemotion", (event) => {
  console.log("Device Motion:", event.acceleration.x, event.acceleration.y, event.acceleration.z);
});
```

##### 18. [Web Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API):
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

##### 19. [Web Payment Request API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API):
```javascript
const supportedInstruments = [{ supportedMethods: 'basic-card' }];
const paymentDetails = { total: { label: 'Total', amount: { currency: 'USD', value: '10.00' } } };
const paymentPromise = new PaymentRequest(supportedInstruments, paymentDetails);

paymentPromise.show().then(paymentResponse =>
  paymentResponse.complete('success')
);
```

<hr>




### UI/UX Design:

<table>
  <tr>
    <th>Mockups</th>
    <th>3D</th>
    <th>Widgets</th>
    <th>Grid Layout</th>
    <th>Typography</th>
    <th>Accessibility</th>
    <th>Animation</th>
    <th>Others</th>
  </tr>
  <tr>
    <td><a href="https://www.figma.com/community/plugin/817043359134136295">Mockup</a></td>
    <td><a href="https://www.figma.com/community/plugin/1260632020336566834">Simple3D</a></td>
    <td><a href="https://www.figma.com/community/widget/1099808304417613104">Navigate</a></td>
    <td><a href="https://www.figma.com/community/plugin/983672137155100557">Token Space 8</a></td>
    <td><a href="https://www.figma.com/community/plugin/739825414752646970">Typescales</a></td>
    <td><a href="https://www.figma.com/community/plugin/733159460536249875">A11y</a></td>
    <td><a href="https://www.figma.com/community/plugin/1077659774432109711">SVG Motion</a></td>
    <td><a href="https://www.figma.com/community/plugin/739659977030056719">Avatars</a></td>
  </tr>
</table>

- [x] [Figma Web](https://www.figma.com)
- [x] [Figma App](https://desktop.figma.com/win/FigmaSetup.exe)

##### Mockups:
- [x] [Mockup](https://www.figma.com/community/plugin/817043359134136295)
- [x] [Mockuuups Studio](https://www.figma.com/community/plugin/786250770157843670)
- [x] [Artboard Studio Mockups](https://www.figma.com/community/plugin/750673765607708804)
- [x] [Angle Mockups](https://www.figma.com/community/plugin/778645840235495725)
- [x] [MockRocket – 3D Mockups](https://www.figma.com/community/plugin/1051242643585430631)
- [x] [Clay Mockups 3D](https://www.figma.com/community/plugin/819335598581469537)
- [x] [Rotato 3D Mockups + Explosions](https://www.figma.com/community/plugin/1009741687635558607)
- [x] [Easy Mockup](https://www.figma.com/community/plugin/1180592708021765520)
- [x] [A Little Bit Mockup](https://www.figma.com/community/plugin/1149987037748021167)

##### 3D:
- [x] [Simple3D](https://www.figma.com/community/plugin/1260632020336566834)
- [x] [Oblique](https://www.figma.com/community/plugin/876352455198080607)
- [x] [Vector to 3D](https://www.figma.com/community/plugin/1264600219316901594)
- [x] [3D Shape Generator](https://www.figma.com/community/plugin/1224199081556506234)
- [x] [Globe 3D](https://www.figma.com/community/plugin/977567760148608604)
- [x] [Fig3D](https://www.figma.com/community/plugin/946020080871644950)
- [x] [Fast Isometric](https://www.figma.com/community/plugin/1249759048471403961)
- [x] [3D Wave](https://www.figma.com/community/plugin/1026141971534783843)

##### Widgets:
- [x] [Navigate](https://www.figma.com/community/widget/1099808304417613104)
- [x] [Simple Vote](https://www.figma.com/community/widget/1031261785662682451)
- [x] [Activity Tracker](https://www.figma.com/community/widget/1026880323669555103)
- [x] [Import PDF](https://www.figma.com/community/widget/1064675123479620100)
- [x] [Voice Memo](https://www.figma.com/community/widget/1100947233945489758)
- [x] [Photo Booth](https://www.figma.com/community/widget/1030479012894344777)
- [x] [Calculator](https://www.figma.com/community/widget/1117624863659822884)
- [x] [Asana](https://www.figma.com/community/widget/1098405969270214551)

##### Grid Layout:
- [x] [Token Space 8](https://www.figma.com/community/plugin/983672137155100557)
- [x] [Auto Layout Grids](https://www.figma.com/community/plugin/1017842387720709543)
- [x] [Grid System](https://www.figma.com/community/plugin/1033367904576323011)
- [x] [Grids Generator](https://www.figma.com/community/plugin/841313026689642442)
- [x] [12 Column Grid](https://www.figma.com/community/plugin/1235599430244558186)
- [x] [AutoGrid](https://www.figma.com/community/plugin/817474150404549708)
- [x] [Figma to Bootstrap 5](https://www.figma.com/community/plugin/1287660587112027215)
- [x] [Layout Grid Visualizer](https://www.figma.com/community/plugin/831003768229656707)

##### Typography:
- [x] [Typescales](https://www.figma.com/community/plugin/739825414752646970)
- [x] [Typestyles](https://www.figma.com/community/plugin/803311677045533625)
- [x] [Textyles](https://www.figma.com/community/plugin/804843548882105498)
- [x] [Typescale](https://www.figma.com/community/plugin/967802396210455992)
- [x] [Text Styles Generator](https://www.figma.com/community/plugin/759472336242530542)
- [x] [Variable Fonts](https://www.figma.com/community/plugin/966184368629063440)
- [x] [Aa Scale](https://www.figma.com/community/plugin/1242946360312220414)

##### Accessibility:
- [x] [A11y](https://www.figma.com/community/plugin/733159460536249875)
- [x] [Color Blind](https://www.figma.com/community/plugin/733343906244951586)
- [x] [Stark](https://www.figma.com/community/plugin/732603254453395948)
- [x] [Contrast](https://www.figma.com/community/plugin/748533339900865323)
- [x] [Text Resizer](https://www.figma.com/community/plugin/892114953056389734)
- [x] [Adee](https://www.figma.com/community/plugin/931280467863251825)
- [x] [Low Vision](https://www.figma.com/community/plugin/940423402083252469)
- [x] [Able](https://www.figma.com/community/plugin/734693888346260052)

##### Animation:
- [x] [SVG Motion](https://www.figma.com/community/plugin/1077659774432109711)
- [x] [LottieFiles](https://www.figma.com/community/plugin/809860933081065308)
- [x] [Motion](https://www.figma.com/community/plugin/889777319208467032)
- [x] [Parallax](https://www.figma.com/community/plugin/1166980815207476504)
- [x] [Figmotion](https://www.figma.com/community/plugin/733025261168520714)
- [x] [Physics Animation](https://www.figma.com/community/plugin/1051790240828992953)
- [x] [Beatflyer](https://www.figma.com/community/plugin/776923340646658146)
- [x] [Blazy](https://www.figma.com/community/plugin/1278086746813211814)

##### Others:
- [x] [Avatars](https://www.figma.com/community/plugin/739659977030056719)
- [x] [EOS Icons](https://www.figma.com/community/plugin/1131638845835688020)
- [x] [Export Images](https://www.figma.com/community/plugin/1073791321657719341)
- [x] [Mesh Gradient](https://www.figma.com/community/plugin/958202093377483021)
- [x] [Simple Icons](https://www.figma.com/community/plugin/1149614463603005908)

<hr>




### APIs:
- [x] https://github.com/marcelscruz/public-apis
- [x] https://www.jsonapi.co/public-api
- [x] https://any-api.com

<hr>




### GitHub Student Developer Pack:
- [x] [Benefits](https://education.github.com/pack)
- [x] [Apply Here](https://education.github.com/discount_requests/application)

<hr>




### Visual Studio:

- [x] [Download Visual Studio Code](https://code.visualstudio.com)

##### Themes and Icons:
- [x] [Theme](https://marketplace.visualstudio.com/items?itemName=tal7aouy.theme)
- [x] [Atom Material Icons](https://marketplace.visualstudio.com/items?itemName=AtomMaterial.a-file-icon-vscode)
- [x] [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

##### Extensions:
- [x] [Alphabetical Sorter](https://marketplace.visualstudio.com/items?itemName=ue.alphabetical-sorter)
- [x] [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [x] [Auto Complete Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-complete-tag)
- [x] [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [x] [vscode-pdf](https://marketplace.visualstudio.com/items?itemName=tomoki1207.pdf)
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

<hr>




### Resources:
- [x] [MDN Web Docs](https://developer.mozilla.org/en-US)
- [x] [DevDocs](https://devdocs.io)
- [x] [W3Schools](https://www.w3schools.com)
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
- [x] [Hex Color Codes with Transparency](https://gist.github.com/lopspower/03fb1cc0ac9f32ef38f4)
- [x] [CSS Filter Generator](https://codepen.io/sosuke/pen/Pjoqqp)

<hr>




### Courses and Learning Materials:

##### LinkedIn Learning:
- [x] [Linux](https://www.linkedin.com/learning/topics/linux-2)
- [x] [Project Management](https://www.linkedin.com/learning/topics/project-management)
- [x] [Professional Development](https://www.linkedin.com/learning/topics/professional-development)
- [x] [Web Development](https://www.linkedin.com/learning/topics/web-development)
- [x] [Git](https://www.linkedin.com/learning/topics/git)
- [x] [APIs](https://www.linkedin.com/learning/topics/apis)
- [x] [AWS](https://www.linkedin.com/learning/topics/amazon-web-services)
- [x] [SQL](https://www.linkedin.com/learning/topics/sql)
- [x] [Python](https://www.linkedin.com/learning/topics/python)
- [x] [JavaScript](https://www.linkedin.com/learning/topics/javascript)
- [x] [Node.js](https://www.linkedin.com/learning/topics/node-js)
- [x] [React.js](https://www.linkedin.com/learning/topics/react-js)
- [x] [User Experience](https://www.linkedin.com/learning/topics/user-experience)
- [x] [Software Development](https://www.linkedin.com/learning/topics/software-development)
- [x] [Graphic Design](https://www.linkedin.com/learning/topics/graphic-design)
- [x] [Photoshop](https://www.linkedin.com/learning/topics/photoshop)
- [x] [Office 365](https://www.linkedin.com/learning/topics/office-365)
- [x] [LinkedIn](https://www.linkedin.com/learning/topics/linkedin)

##### YouTube:
- [x] [Anson The Developer](https://www.youtube.com/@ansonthedev)
- [x] [CS50](https://www.youtube.com/@cs50)
- [x] [Fireship](https://www.youtube.com/@Fireship)
- [x] [FreeCodeCamp](https://www.youtube.com/@freecodecamp)
- [x] [GitHub](https://www.youtube.com/@GitHub)
- [x] [Kevin Powell](https://www.youtube.com/@KevinPowell)
- [x] [Kevin Stratvert](https://www.youtube.com/@KevinStratvert)
- [x] [Facebook Open Source](https://www.youtube.com/@FacebookOpenSource)
- [x] [Microsoft Azure](https://www.youtube.com/@MicrosoftAzure)
- [x] [Traversy Media](https://www.youtube.com/@TraversyMedia)

<hr>




### Frameworks / Tools:

##### CSS:
- [x] [Tailwind CSS](https://tailwindcss.com/docs/installation)
- [x] [Bootstrap](https://getbootstrap.com/docs/5.3/getting-started/download)
- [x] [CSS Loaders](https://css-loaders.com)

##### Fonts:
- [x] [Google Fonts](https://fonts.google.com)
- [x] [WhatTheFont](https://www.myfonts.com/pages/whatthefont)

##### Icons / SVG:
- [x] [Font Awesome](https://fontawesome.com/search?o=r&m=free)
- [x] [Simple Icons](https://github.com/simple-icons/simple-icons)
- [x] [IconMonstr](https://iconmonstr.com)
- [x] [Icons8](https://icons8.com)
- [x] [Vector Logo Zone](https://www.vectorlogo.zone/logos/index.html)
- [x] [World Vector Logo](https://worldvectorlogo.com)

##### Images / Videos:
- [x] [Unsplash](https://unsplash.com)
- [x] [Freepik](https://www.freepik.com)
- [x] [Shields.io](https://shields.io)
- [x] [Mesh Gradient](https://meshgradient.in)

##### Grammar:
- [x] [Ginger Grammer Checker](https://www.gingersoftware.com/grammarcheck)
- [x] [Quillbot Grammar Checker](https://quillbot.com/grammar-check)

##### AI
- [x] [Google Bard](https://bard.google.com/chat)
- [x] [ChatGPT](https://chat.openai.com)
- [x] [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [x] [Kive.ai](https://kive.ai)
- [x] [tl;dv](https://tldv.io)
- [x] [Playground.ai](https://playgroundai.com)
- [x] [Beautiful.ai](https://www.beautiful.ai)
- [x] [Generated Photos](https://generated.photos)
- [x] [Leonardo.ai](https://app.leonardo.ai)
- [x] [Bing Image Creator](https://www.bing.com/images/create)

##### Database:
- [x] [Supabase](https://github.com/supabase/supabase)

<hr>




### Optimization:

##### Images
- [x] [postimages](https://postimages.org)
- [x] [imgbb](https://imgbb.com)
- [x] [tinypng](https://tinypng.com)

##### Performance
- [x] [pagespeed](https://pagespeed.web.dev)

##### Analytics
- [x] [Google Analytics](https://analytics.google.com/analytics/web)

##### SEO
- [x] [Google Search Console](https://search.google.com/search-console/welcome)
- [x] [Bing Webmasters](https://www.bing.com/webmasters)

##### Meta Tags
- [x] [Social Share Preview](https://socialsharepreview.com)
- [x] [MetaTags.io](https://metatags.io)

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
- [x] CRUD Operation Website
- [x] Event Countdown Timer
- [x] Random HEX Color Code Generator (with Preview)
- [x] Simple Firefox / Chrome Extensions
