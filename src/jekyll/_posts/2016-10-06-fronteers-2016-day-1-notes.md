---
title: "Fronteers 2016: Day One"
date: 2016-10-06
intro: My notes for the 1st day of Fronteers 2016.
lead: My notes for the 1st day of Fronteers 2016.
---

## Ire Aderinokun: Progressive Enhancement and CSS
- http://bitsofco.de since 1.5 yrs
- Progessive enhancement usually about JavaScript.
- 2003: Safari 1.0, Phoenix (firefox), IE winning (95%)

### Graceful degradation
- 2003: Graceful degradation: provide certain level of user experience in modern browsers, lower level in older browsers.
- March 11, 2003: Stephen Champeon, "Inclusive Webdesign For The Future" outlines problems with graceful degradation
- GD: Doesn't straddle technology inflection points well
- GD: Many designers don't test anything but one version back
- GD: Does not adddress different needs of different audeiences
- GD: Expensive to retrofit to new alternate devices
- GD: Whatever is 'good enough' usually rules
- "Webdesign must mature and accept the developments of the past several years."
- "Goal is not to dazzle, but deliver info to the weidest audience"

### Progressive enhancement
1. Basic functionality should be available
2. Sparse, semantic markup should contains all content, content should be defined in plain text in markup
3. Enhanced layout can be provided by CSS stylesheets
4. Enhanced behaviour can be provided by unobtrusive JavaScript
5. End-user web browser preferences should be respected

### Why is Progressive Enhancement important today?
- More of everything: browsers, devices, ...
- More tools to build sites
- More people online (K 1.000.000.000 vs. > 3.500.000.00)
- The web is still open

### Progressive Enhancement & JavaScript
- What can go wrong?
- JavaScript disabled in browser --> Make website functional without JavaScript
- Browser does not support feature --> Feature detection / polyfill

### Progressive Enhancement & HTML
- Browser does not understand semantic meaning --> add ARIA roles

### What about CSS: the problem with Progressive Enhancement and CSS
- Can't prepare for unsupported features
- No built-in fallback
- Debugging CSS is hard

### Todays's solution for Progressive Enhancemnt with CSS
- Start with sensible HTML
- Don't change the order of elements via CSS
- Don't target elements in CSS
- Take advantage of the cascade
- Fallback in CSS: vendor prefixes etc.
- Mobile first strategy - min-width based media queries.
- Use Flexbox, designed to be a progressive enhancement
- Separate stylesheets for different browsers as a last resort

### CSS Feature Queries
- Conditional rules in CSS
- @supports (foo:bar){ ... }
- @supports ((foo:bar) or (bar:baz)){ ... }
- @supports not (foor:bar){ ... }
- Good support, except for IE/Opera Mini
- Four scenarios: (!)support CSS feature + (!)support feature queries

### The world in 2030
- Even more stuff
- More browsers (VR, watches, ...)
- More technologies: Angular 23.0

## Nadieh Bremer: Hacking The Visual Norm
- @nadiehbremer
- Originally astronomer, now data visualisation at Adyen.
- visualcinnamon.com
- D3 is the default JavaScript library for Data Visualisation

### Adyen
- Handles payments
- Middleman between store and you
- Catch fraude
- Hard to choose colors: usually just 'design', not data (darker green is not more important than light green)

## G. Scott Olson: How you do what you do is who you are
- Works at FiftyThree (Paper/Pencil/Mix)
- Hybrid designer/developer (Maker)
- One idea can become a thousand ideas

### React
- Using React to improve user experience (images/forms/user-input)
- Paper for Web is a React App + NodeJS + Stylus + Webpack (build = 450kb)
- React All The Things!
- What parts of app need to be seamless?

### Preloading images
- Requirement for React = JavaScript available
- Image preloading via Image API (new Image())
- Images in grid, images might not load in correct order.
- Set fixed height using spacer images
- Spacer images = extra requests etc. Not managable.
- What about SVG?
- Images outside of viewport may load earlier than images inside viewport

### Fluid text inputs
- Resizes when content changes
- Must resize dynamically
- Allow text selection
- Do not break understanding of text inputs, what user expect
- Must use placeholder text consistently across browsers (different behaviour in browsers)
- Must support touch events
- Contenteditable? Allows line breaks, paste with formatting etc. Not an option.

### Image pyramids
- Images at different resolution
- Util in Javascript to get best image based on container dimensions
- S3 used to manage images

## Nolan Lawson: Offline, progressive and multithreaded: a peek at the web apps of the future
- @nolanlawson
- Works at Microsoft Edge
- Look at web app development, extrapolate from past to see where we're going.

### Progressive web apps
- Offline/progressive/multithreaded
- Not focus on technical details, but on history.
- If you were building a web app 15 years ago, probably using Flash
- HTML in competition with technologies like Flash/Silverlight
- HTML5 is a response to Flash/Silverlight/etc.
- Today: probably using webtechnologies
- We won on desktop, just in time - when mobile became big.
- Mail on desktop: 90% web, 10% native
- Mail on mobile: 10% web, 90% native

### Offline
- PouchDB: wrapper for indexedDB (store data locally, sync when connection)
- "Offline-first" is not really about about being in the subway etc.
- "Offline-first" is about speed.
- Memory = superfast, disk = slower, network = very slow
- PHP.net autosuggest = local storage, very very fast.
- "The webplatform has always had two solutions to a problem; the old deprecated one you shouldn't use and the new which isn't ready yet."
- Static data: old way is AppCache, new way is Cache API (Service Worker)
- Dynamic data: old way is LocalStorage/WebSQL, new way is IndexedDB
- Old ways were very specificly implemented, new way is more designed with web in mind - to build libraries upon.

### Progressive
- Website becomes a progressive web app.
- In 2016 it's okay to make a website that does not work without JavaScript
- Web = 3 pillars: HTML/CSS/JavaSCript. Can't really pull one out
- Connectivity is problem, not old browsers/no JavaScript
- Progressive rendering: not loading one big app.js
- Critical HTML/CSS, then download more stuff
- Ember/Server-side React/Angular2 isolated render do progressive rendering

### Multithread
- Jank: web is single threaded, apps/sites do too much
- Hardware (midrange) may not be very fast, but all have 4 cores
- Webworkers do vast majority of app logic
- UI thread does UI/effects
- Webworkers might be overhead unless working with big data

## Martin Split: Multi-user WebVR (or: Wait, who are these people?)
- @g33konaut
- VR is hot: Oculus, Steam/Valve, HTC Vive, Google Daydream
- VR is great for education, marketing, construction/architecture, healthcare, design/arts...
- VR risks regression: exclusivity rights (Oculus DRM to avoid being able to use on Vive)
- WebVR
- 360 panorma = WebVR's Hello World
- How to transfer from environment A to environent B?

### Where are we with WebVR?
- Current draft 1.1
- Love from Mozilla/Google/Microsoft/Samsung
- Experimental browser builds
- Gamepad API Extension
- No DOM yet.

### The extremes
- No DOM events
- How to move
- How to interact
- Position tracking on Vive
- Moving far?
- Handling hands?

## Other input
- LEAPmotion
- Myo
- Microsoft Kienct
- Intel Realsense

## Lodewijk Nauta: Big Data, Big Impact
- A picture paints a 1000 words...
- ...but paint the right picture!

## Monika Piotrowitcz: Scaling Front-end Development
- Director of FED at Shopify

### Defining FED
- HTML/CSS/JS
- Node/Webpack/SASS/Gulp/Angular/...
- How do you build a team around chaos?

### No FED
- No owner of bridge between Design and Back-end.
- Inconsistent/buggy UI.
- Spaghetti code
- Hard to maintain/iterate
- Not accessible/performant/responsive

### Language styleguides
- Code standards
- Consistency is key
- Helps read each other's code
- Helps you read your own code in the future
- Encourage you to think about your way of coding

### Code reviews
- Use linters/hinters
- Every line of code is reviewed before release
- Shared definition of quality
- Dealing with existing code?
- Build a culture of feedback/sharing

### Pattern libraries
- A way to pool our efforts
- Make it possible to share code automatically
- A starting point for new projects
- A default stack (SASS/Rails/...)
- Guidelines for dealing with responsiveness
- Performance standards/language tooling
- Accessibility standards

### UI Library
- Core application patterns
- Solved for specific use cases (opinionated)
- Look to design to determine what are patterns and what are not
- Build API to have a single source of truth

## Peter Gasston: Surveying the Landscape
- Rehab Studio
- Realistic danger that the web will be marginalized in favour of apps
- App-only strategies

### Advertising/tracking/making money

- Web filled with tracking/ads: 50+ percent of bandwidth
- 1 in 2 users say ads etc have stopped them from using a website
- 21% of users block ads from mobile web
- Monetisation: free, ad-supported isn't sustainable anymore.

### Move from web to apps
- "The idea won't be to start a website. That will be dead. The individual website is dead."
- "A lot of designers are still focussed on website - not certain that's a growth business anymore."
- $0.85 of every $1 spent on advertising on Google/Facebook.
- Platforms that matured on the web are leaving it behind (Facebook, Twitter). Embedding own content instead of external content.

### New users
- New users come online, straight to mobile. No desktop, no laptop, no web
- 1 hour of minimum wage = data to visit 15 websites
- 15% of avg month income = 1GB data in Myanmar
- Users use pre-paid data. They feel every MB. Apps like FB can optimize
- Users identify as 'using Facebook' instead of 'using the internet'
- Facebook becomes the mobile internet

### Positive
- Still a lot of users (Google Chrome mobile 1+ billion users per month)
- Shopping on the web is still bigger than via apps