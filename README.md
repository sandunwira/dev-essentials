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

- [x] [Figma Web](https://www.figma.com)
- [x] [Figma App](https://desktop.figma.com/win/FigmaSetup.exe)

| Mockups | 3D | Widgets | Grid Layout | Typography | Accessibility | Animation | Others |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [Mockup](https://www.figma.com/community/plugin/817043359134136295) | [Simple3D](https://www.figma.com/community/plugin/1260632020336566834) | [Navigate](https://www.figma.com/community/widget/1099808304417613104) | [Token Space 8](https://www.figma.com/community/plugin/983672137155100557) | [Typescales](https://www.figma.com/community/plugin/739825414752646970) | [A11y](https://www.figma.com/community/plugin/733159460536249875) | [SVG Motion](https://www.figma.com/community/plugin/1077659774432109711) | [Avatars](https://www.figma.com/community/plugin/739659977030056719) |
| [Mockuuups Studio](https://www.figma.com/community/plugin/786250770157843670) | [Oblique](https://www.figma.com/community/plugin/876352455198080607) | [Simple Vote](https://www.figma.com/community/widget/1031261785662682451) | [Auto Layout Grids](https://www.figma.com/community/plugin/1017842387720709543) | [Typestyles](https://www.figma.com/community/plugin/803311677045533625) | [Color Blind](https://www.figma.com/community/plugin/733343906244951586) | [LottieFiles](https://www.figma.com/community/plugin/809860933081065308) | [EOS Icons](https://www.figma.com/community/plugin/1131638845835688020) |
| [Artboard Studio Mockups](https://www.figma.com/community/plugin/750673765607708804) | [Vector to 3D](https://www.figma.com/community/plugin/1264600219316901594) | [Activity Tracker](https://www.figma.com/community/widget/1026880323669555103) | [Grid System](https://www.figma.com/community/plugin/1033367904576323011) | [Textyles](https://www.figma.com/community/plugin/804843548882105498) | [Stark](https://www.figma.com/community/plugin/732603254453395948) | [Motion](https://www.figma.com/community/plugin/889777319208467032) | [Export Images](https://www.figma.com/community/plugin/1073791321657719341) |
| [Angle Mockups](https://www.figma.com/community/plugin/778645840235495725) | [3D Shape Generator](https://www.figma.com/community/plugin/1224199081556506234) | [Import PDF](https://www.figma.com/community/widget/1064675123479620100) | [Grids Generator](https://www.figma.com/community/plugin/841313026689642442) | [Typescale](https://www.figma.com/community/plugin/967802396210455992) | [Contrast](https://www.figma.com/community/plugin/748533339900865323) | [Parallax](https://www.figma.com/community/plugin/1166980815207476504) | [Mesh Gradient](https://www.figma.com/community/plugin/958202093377483021) |
| [MockRocket – 3D Mockups](https://www.figma.com/community/plugin/1051242643585430631) | [Globe 3D](https://www.figma.com/community/plugin/977567760148608604) | [Voice Memo](https://www.figma.com/community/widget/1100947233945489758) | [12 Column Grid](https://www.figma.com/community/plugin/1235599430244558186) | [Text Styles Generator](https://www.figma.com/community/plugin/759472336242530542) | [Text Resizer](https://www.figma.com/community/plugin/892114953056389734) | [Figmotion](https://www.figma.com/community/plugin/733025261168520714) | [Simple Icons](https://www.figma.com/community/plugin/1149614463603005908) |
| [Clay Mockups 3D](https://www.figma.com/community/plugin/819335598581469537) | [Fig3D](https://www.figma.com/community/plugin/946020080871644950) | [Photo Booth](https://www.figma.com/community/widget/1030479012894344777) | [AutoGrid](https://www.figma.com/community/plugin/817474150404549708) | [Variable Fonts](https://www.figma.com/community/plugin/966184368629063440) | [Adee](https://www.figma.com/community/plugin/931280467863251825) | [Physics Animation](https://www.figma.com/community/plugin/1051790240828992953) | ... |
| [Rotato 3D Mockups + Explosions](https://www.figma.com/community/plugin/1009741687635558607) | [Fast Isometric](https://www.figma.com/community/plugin/1249759048471403961) | [Calculator](https://www.figma.com/community/widget/1117624863659822884) | [Figma to Bootstrap 5](https://www.figma.com/community/plugin/1287660587112027215) | [Aa Scale](https://www.figma.com/community/plugin/1242946360312220414) | [Low Vision](https://www.figma.com/community/plugin/940423402083252469) | [Beatflyer](https://www.figma.com/community/plugin/776923340646658146) | ... |
| [Easy Mockup](https://www.figma.com/community/plugin/1180592708021765520) | [3D Wave](https://www.figma.com/community/plugin/1026141971534783843) | [Asana](https://www.figma.com/community/widget/1098405969270214551) | [Layout Grid Visualizer](https://www.figma.com/community/plugin/831003768229656707) | ... | [Able](https://www.figma.com/community/plugin/734693888346260052) | [Blazy](https://www.figma.com/community/plugin/1278086746813211814) | ... |
| [A Little Bit Mockup](https://www.figma.com/community/plugin/1149987037748021167) | ... | ... | ... | ... | ... | ... | ... |

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

| Extensions | Themes and Icons |
| --- | --- |
| [Alphabetical Sorter](https://marketplace.visualstudio.com/items?itemName=ue.alphabetical-sorter) | [Theme](https://marketplace.visualstudio.com/items?itemName=tal7aouy.theme) |
| [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag) | [Atom Material Icons](https://marketplace.visualstudio.com/items?itemName=AtomMaterial.a-file-icon-vscode) |
| [Auto Complete Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-complete-tag) | [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons) |
| [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag) | ... |
| [vscode-pdf](https://marketplace.visualstudio.com/items?itemName=tomoki1207.pdf) | ... |
| [Color Info](https://marketplace.visualstudio.com/items?itemName=bierner.color-info) | ... |
| [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) | ... |
| [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) | ... |
| [HTML Boilerplate](https://marketplace.visualstudio.com/items?itemName=sidthesloth.html5-boilerplate) | ... |
| [HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css) | ... |
| [indent-rainbow](https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow) | ... |
| [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) | ... |
| [Lorem Ipsum](https://marketplace.visualstudio.com/items?itemName=Tyriar.lorem-ipsum) | ... |
| [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) | ... |
| [npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense) | ... |
| [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense) | ... |
| [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) | ... |

<hr>




### Resources:

| Main | GitHub | GeeksforGeeks | FreeCodeCamp | W3Schools | Others |
| --- | --- | --- | --- | --- | --- |
| [MDN Web Docs](https://developer.mozilla.org/en-US) | [tiimgreen/github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet) | [HTML](https://www.geeksforgeeks.org/html-cheat-sheet-a-basic-guide-to-html) | [HTML (Search)](https://www.freecodecamp.org/news/search/?query=html) | [HTML](https://www.w3schools.com/html/default.asp) | [Hex Color Codes with Transparency](https://gist.github.com/lopspower/03fb1cc0ac9f32ef38f4) |
| [Google Developers](https://developers.google.com) | [microsoft/Web-Dev-For-Beginners](https://github.com/microsoft/Web-Dev-For-Beginners) | [CSS](https://www.geeksforgeeks.org/css-cheat-sheet-a-basic-guide-to-css) | [HTML](https://www.freecodecamp.org/news/tag/html) | [CSS](https://www.w3schools.com/css/default.asp) | [CSS Filter Generator](https://codepen.io/sosuke/pen/Pjoqqp) |
| [GitHub Docs](https://docs.github.com/en) | [florinpop17/app-ideas](https://github.com/florinpop17/app-ideas) | [JavaScript](https://www.geeksforgeeks.org/javascript-cheat-sheet-a-basic-guide-to-javascript) | [HTML5](https://www.freecodecamp.org/news/tag/html5) | [JavaScript](https://www.w3schools.com/js/default.asp) | ... |
| [DevDocs](https://devdocs.io) | [thedaviddias/Front-End-Checklist](https://github.com/thedaviddias/Front-End-Checklist) | ... | [CSS (Search)](https://www.freecodecamp.org/news/search/?query=css) | ... | ... |
| [W3Schools](https://www.w3schools.com) | [marcobiedermann/search-engine-optimization](https://github.com/marcobiedermann/search-engine-optimization) | ... | [CSS](https://www.freecodecamp.org/news/tag/css) | ... | ... |
| [Stack Overflow](https://stackoverflow.com) | [levinunnink/html-form-to-google-sheet](https://github.com/levinunnink/html-form-to-google-sheet) | ... | [JavaScript (Search)](https://www.freecodecamp.org/news/search/?query=javascript) | ... | ... |
| [CSS Tricks](https://css-tricks.com) | [freeCodeCamp/freeCodeCamp](https://github.com/freeCodeCamp/freeCodeCamp) | ... | [JavaScript](https://www.freecodecamp.org/news/tag/javascript) | ... | ... |
| [freeCodeCamp](https://www.freecodecamp.org) | [joshbuchea/HEAD](https://github.com/joshbuchea/HEAD) | ... | ... | ... | ... |
| [CodePen](https://codepen.io) | [phuocng/html-dom](https://github.com/phuocng/html-dom) | ... | ... | ... | ... |

<hr>




### Courses and Learning Materials:

| LinkedIn Learning | YouTube |
| --- | --- |
| [Linux](https://www.linkedin.com/learning/topics/linux-2) | [Anson The Developer](https://www.youtube.com/@ansonthedev) |
| [Project Management](https://www.linkedin.com/learning/topics/project-management) | [CS50](https://www.youtube.com/@cs50) |
| [Professional Development](https://www.linkedin.com/learning/topics/professional-development) | [Fireship](https://www.youtube.com/@Fireship) |
| [Web Development](https://www.linkedin.com/learning/topics/web-development) | [FreeCodeCamp](https://www.youtube.com/@freecodecamp) |
| [Git](https://www.linkedin.com/learning/topics/git) | [GitHub](https://www.youtube.com/@GitHub) |
| [APIs](https://www.linkedin.com/learning/topics/apis) | [Kevin Powell](https://www.youtube.com/@KevinPowell) |
| [AWS](https://www.linkedin.com/learning/topics/amazon-web-services) | [Kevin Stratvert](https://www.youtube.com/@KevinStratvert) |
| [SQL](https://www.linkedin.com/learning/topics/sql) | [Facebook Open Source](https://www.youtube.com/@FacebookOpenSource) |
| [Python](https://www.linkedin.com/learning/topics/python) | [Microsoft Azure](https://www.youtube.com/@MicrosoftAzure) |
| [JavaScript](https://www.linkedin.com/learning/topics/javascript) | [Traversy Media](https://www.youtube.com/@TraversyMedia) |
| [Node.js](https://www.linkedin.com/learning/topics/node-js) | ... |
| [React.js](https://www.linkedin.com/learning/topics/react-js) | ... |
| [User Experience](https://www.linkedin.com/learning/topics/user-experience) | ... |
| [Software Development](https://www.linkedin.com/learning/topics/software-development) | ... |
| [Graphic Design](https://www.linkedin.com/learning/topics/graphic-design) | ... |
| [Photoshop](https://www.linkedin.com/learning/topics/photoshop) | ... |
| [Office 365](https://www.linkedin.com/learning/topics/office-365) | ... |
| [LinkedIn](https://www.linkedin.com/learning/topics/linkedin) | ... |

<hr>




### Frameworks / Tools:

| CSS | Fonts | Icons / SVG | Images / Videos | Grammar | AI | Database |
| --- | --- | --- | --- | --- | --- | --- |
| [Tailwind CSS](https://tailwindcss.com) | [Google Fonts](https://fonts.google.com) | [Font Awesome](https://fontawesome.com/search?o=r&m=free) | [Unsplash](https://unsplash.com) | [Ginger Grammer Checker](https://www.gingersoftware.com/grammarcheck) | [Google Bard](https://bard.google.com/chat) | [Supabase](https://github.com/supabase/supabase) |
| [Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction) | [WhatTheFont](https://www.myfonts.com/pages/whatthefont) | [Simple Icons](https://github.com/simple-icons/simple-icons) | [Freepik](https://www.freepik.com) | [Quillbot Grammar Checker](https://quillbot.com/grammar-check) | [ChatGPT](https://chat.openai.com) | ... |
| [CSS Loaders](https://css-loaders.com) | ... | [IconMonstr](https://iconmonstr.com) | [Shields.io](https://shields.io) | ... | [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) | ... |
| ... | ... | [Icons8](https://icons8.com) | [Mesh Gradient](https://meshgradient.in) | ... | [Kive.ai](https://kive.ai) | ... |
| ... | ... | [World Vector Logo](https://worldvectorlogo.com) | ... | ... | [tl;dv](https://tldv.io) | ... |
| ... | ... | [Vector Logo Zone](https://www.vectorlogo.zone/logos/index.html) | ... | ... | [Playground.ai](https://playgroundai.com) | ... |
| ... | ... | ... | ... | ... | [Beautiful.ai](https://www.beautiful.ai) | ... |
| ... | ... | ... | ... | ... | [Generated Photos](https://generated.photos) | ... |
| ... | ... | ... | ... | ... | [Leonardo.ai](https://app.leonardo.ai) | ... |
| ... | ... | ... | ... | ... | [Bing Image Creator](https://www.bing.com/images/create) | ... |

<hr>




### Optimization:

| Images | Performance | Analytics | SEO | Meta Tags |
| --- | --- | --- | --- | --- |
| [postimages](https://postimages.org) | [pagespeed](https://pagespeed.web.dev) | [Google Analytics](https://analytics.google.com/analytics/web) | [Google Search Console](https://search.google.com/search-console/welcome) | [Social Share Preview](https://socialsharepreview.com) |
| [imgbb](https://imgbb.com) | ... | ... | [Bing Webmasters](https://www.bing.com/webmasters) | [MetaTags.io](https://metatags.io) |
| [tinypng](https://tinypng.com) | ... | ... | ... | ... |

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
