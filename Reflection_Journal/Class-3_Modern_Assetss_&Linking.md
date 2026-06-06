# Theory

## Explain step-by-step how you would optimize a 5 MB PNG for a hero image for a production website in 2026. Include: formats, tools, and reasoning behind each choice.

### Step by step to optimize it for a production website
---

The image need to optimize and keep original aspect ratio

1. Check the original dimension and aspect ratio of the image.

2. Convert it to webp using https://towebp.io/ or any other tools.
        
        Reason: PNGs contain high-quality, detailed image data, their larger file size means slower page loading times and responsiveness. Supports transparency & animation , Broad browser support Drop-in replacement.
3. Done with Conversion. If the image is in suitable size (around 1800px to 1200px), it is suitable for desktop screen and resize or crop for mobile size also(around 800px to 400px ).

        Reason: Resizing it stops the browser from working hard to scale down a gigantic image, which saves bytes
4.  May also convert to AVIF to save more sizes.

        Reason: AVIF can offer 30-50% better compression than WebP, Excellent quality at low sizes
   The 5mb png is too large and it will wastes bandwidth and slows load time.
### What is **srcset** and when you'd use it. Create a scenario where srcset prevents a problem for mobile users.
---
```srcset``` is an html attribute that let you define multiple versions of same image at different width (400w, 800w, 1200w).
```html 
<img src="image-800.jpg" srcset="image-400.jpg 400w, image-800.jpg 800w, image-1200.jpg 1200w"  sizes="(max-width: 600px) 400px, (max-width: 1200px) 800px, 1200px" alt="Example image">
```

### rel="noopener" important when using target="_blank"? What security vulnerability does it prevent? Explain in terms a non-technical person would understand.
---


```rel="noopener"``` is a html attribute value that when using with ```target="blank"``` , it prevent the new tab to access the previous tab(i.e originating page) using window.opener , it prevent security vulnerability such Cross-site scripting.

You know when you are on a webpage let say Facebook webpage suddenly a pop-up show on the let say webpage shows your Facebook account is blocked , you click the pop-up, and it open another tab but not knowing that that newly tab is phishing website (phishing website is a fraudulent site designed by cybercriminals to mimic a legitimate, trusted organization—such as your bank, email provider, or an online shopping store. Its primary purpose is to trick you into voluntarily handing over sensitive information like login credentials, credit card numbers, or personal data) , the phishing website can silently change original tab(i.e previous tab) to fake Facebook login page, you might end up typing your username and password, unknowingly handing their data straight to a hacker. 

The ```rel=noopener``` prevents that from happening.

# ⚙️ Engineering Thinking
## You need to display 50 product images on a page. What's your optimization strategy? Consider: lazy loading, format choice, CDN, and responsive sizing.

I will have to make the image size small as possible without affecting the quality of the image to prevent slow load times and high bandwidth usage.

*  Lazy Loading:
Lazy loading is a strategy to identify resources as non-blocking (non-critical) and load these only when needed. Only load images that are in or near the user’s viewport. As the user scrolls down, trigger the loading of subsequent images.This reduces the initial page load time, saves bandwidth, and improves performance, especially for image-heavy websites.

* Format Choice:
modern browsers support new image formats such as WebP and AVIF, which can squeeze out some additional file-size reductions through newer compression algorithms.They provide superior compression and image quality at file sizes up to 35% smaller than JPEG or PNG.
Use of SVG which is great format for logos, digital illustrations, icons, and other pictures. The file size stays the same no matter how large they're ultimately rendered, whereas regular raster graphics files get larger.

* Content Delivery Network (CDN):
CDNs store copies of your images on servers distributed around the world. When someone in Ghana visits your site, they get images from a nearby server in Nigeria rather than from your origin server in, say, US. This geographic proximity can cut image load times by 50% or more for international visitors.

* Responsive Size:
Using same image with different size for different devices
