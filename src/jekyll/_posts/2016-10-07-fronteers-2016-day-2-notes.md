---
title: Fronteers 2016, Day Two
date: 2016-10-06
intro: My notes for the 2nd day of Fronteers 2016.
---

<p class="lead">After visiting the Jam Sessions lorem ipsum dolor sit amet.</p>

## Jason Grigsby: Adapting to Input
- @grigs
- CloudFour

### In the beginning
- Web was formless
- Forms only added when web became commercial
- Web was 640x480> 800x600 > 1024x768 etc.
- Consensual hallucination: instead of us having somebody trick us, we trick ourselves. Makes our lives easier.
- The web never had a fixed canvas.
- Desktop = keyboard, Mobile = touch.

### Time to break free from these assumptions
1. Input is exploding
2. Focus on broad adaption
3. Using Apple as a lens

### History
- 1874: First keyboard
- 1984: Mouse, tracksballs, joysticks
- 1996: Mouse with scrollwheel
- 2005: Cameras in phones/computers
- 2007: iPhone
- 2008: MacBook Air - trackpad/gestures
- 2009+: Gyroscopes, multi-touch trackpad, Siri, Bluetooth LE, fingerprint sensor, NFC, Barometer, 3D Touch
- Every single year new sensors, capabilities, etc.
- We can no longer make assumptions about input based on screensize.

### Input is undetectable
- " I got this. I detect touch."
- Not that easy/possible to accurately detect touch.
- Chrome thinking about enabling touch by default
- Cannot detect mouse, keyboard etc.
- This saves us from ourselves.
- Input is much like Schrodinger's Cat: we don't know what type of input user will use, until they do so: too late for our UI

### Input is...
- exploding
- a continuum
- undetectable
- transient (can change very quickyl)

### Fitt's law
- The larger a target is, the easier it is to select it.
- Every desktop UI should be designed for touch now

### Design for modes of interaction instead of input
- Display density settings in GMail
- Designing for user need, not form factor/input

### Make things accessible
- TV browsers that support d-pad, send arrow key events
- If remote control, support arrow keys = Wrong. Just support arrow keys.

### Design for multiple concurrent inputs
- Examples of Google Maps using touchpad and touch at the same time.
- Don't assume users will only have/use one form of input

### Abstract baseline input
- Don't think of mobile/tablet/desktop ==> small/medium/large
- Need to do something similar to input ==> point, select instead of mousemove, click, touchstart, ...

### Progressively enhance input
- Opportunity is knocking
- We're pretty good at using Geolocation
- Other inputs barely used: compass, gyroscope etc.
- Scan creditcards on iOS
- Remember to support auto-fill (use autocomplete attribute)
- Payment Request API

### Make input part of test plans
- Need to add new ways of input to device lab (Apple Pencil, stylus, ...)

### Overview
1. Design for the largest target by default
2. Design for modes of interaction instead of input
3. Make things accessible
4. Design for multiple conccurrent inputs
5. Abstract baseline input
6. Progressive Enhance input
7. Make input part of testplans

## Barbara Bermes: Cheatsheet to a Lean Website
- Works at Firefox
- @bbinto

### Why should you care about performance
- People don't like to wait
- 79% of shoppers will not return after disappointing experience/performance
- 1 second dlay: 11% fewer page views, 7% loss in conversion, 16% decrease in customer satisfaction, $1.6 billion loss (Amazon)

### Shape a performance culture
- Make everbody aware/care, it's everybody's business
- Say "No" to marketing/... when things will make performance bad
- Celebrate success
- Be transparent of results

### Performance = perception and respect
- Older people will have more patience
- Show respect to users: fast websites make users feel good
- Treat speed as a feature, not a nice to have
- Optimize from a user's perspective

### Measurable performance modules
- Low impact: small images, static conctent
- Medium impact: Some Javascript etc
- Heavy impact: external Javascript, AJAX requests, ...

### Measure first, then optimize
- Performance budget
- Speed index: how fast components load (the lower the better)
- Page Speed: 0-100, 85 is recommended.
- SpeedCurve

### Determine critical path
- Clean HTML
- Remove unused DOM
- Correct order
- No third-party features
- Critical CSS
- Use async/defer for `<script>`

### Reduce bytes
- Minifiy HTML/CSS/JS
- Optimize images
- Avoid Web Fonts (or use a web font loader)
- Use GZip techniques

### Reduce HTTP Requests
- Concatenate where applicable
- Don't blindly use frameworks
- Use image sprites
- Data URI for small images

### Fight latency
- Time it takes for content to be requested and shown
- Reduce HTTP requesst
- Reduce amount of polling
- Critical CSS
- Remove redirects
- Offline storage
- CDN
- HTTP/2

### Make friends with the server
- GZip assets
- Solid cache policy

### Automate perforamnce routines
- Task runners Grunt/Gulp/Maven/Ant
- Include in continuous integration system

## Zell Liew: Building Responsive CSS Components
- https://zellwk.com/

### Modular
- Standardized units for easy construction
- Atomic Design/BEM/Namespacing/OOCSS/SMACSS
- Communicate with your team

### Scalable
- To adjust in amount according to a fixed scale or proportion
- How much do we need to scale?
- Principle of repetition = familarity.
- Shift focus away from design to actual content.
- Limit sizes/scaling.
- Consistent whitespace.
- Different behaviour of component based on location

### Modularity when scaling
- Element Queries
- No valid CSS yet, needs JavaScript

## Scott Helme: CPS STS PKP SRI ETC OMG WTF BBQ

### HTTP/2
- No more image sprites
- No more concatinating
- No more domain sharding
- GeoLocation API only over HTTPS
- getUserMedia() only over HTTPS
- AppCacnhe only over HTTPS
- Brotli Compression, better than GZip
- SEO Boost

### Security headers
- Content-security-policy
- Publc-Key-Pins
- Strict-Transport-Security
- Subresource Integrity

### Content Security Policy
- Local, what MY site allows to load
- Stop content injection (XSX)
- Whitelist which servers content is allowed from
- Upgrade insecure requests: Change http to https
- Without HSTS: Redirect http to https. Costs time.
- With HSTS: Browser goes to https by default, overrides user.

## Sarah Drasner: Functional Animation

## Bruce Lawson: ...

## Leonie Watson: Technologic (Human Afterall) - Accessibility Mix

## Heydon Pickering: Joining Up The Dots