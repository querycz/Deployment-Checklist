# Deployment Checklist ☑️

> Basic deployment checklist before WordPress deployment

## Before Deploy

### .htaccess
- [ ] Force "www" redirect of website/app
- [ ] Enable GZip compression and caching
- [ ] Activate SSL certificate and force HTTPS redirection
	- [ ] Verify that every assets and route is using HTTPS

### Code and Assets
- [ ] Set meta tags (meta description, etc.)
	- [ ] Set Open Graph meta tags
- [ ] Mark key elements according to WAI ARIA
- [ ] Check 404 error page
- [ ] Check CSS for unwanted `@import`
- [ ] Enable HTML minification
- [ ] _(Optional)_ Add lazyloading off images and iframes
- [ ] _(Optional)_ Set JavaScript prioritization
- [ ] Optimize images in Optimage, TinyPNG, SVGOMG (eventuálně ImageOptim, ImageAlpha, Squoosh)
- [ ] Check website/app in IE 11+ and alternative browsers

### WordPress
- [ ] Change admin password
- [ ] Disallow access to readme.html and licence.txt
- [ ] _(Optional)_ Consider disallow access to the authors archive
- [ ] Check image size WordPress prints

### Analytics and SEO
- [ ] Add Google Analytics script
	- [ ] Activate Demography report
	- [ ] Změnit délku uchovávání dat (Služba –> Údaje o měření –> Uchovávání dat)
	- [ ] _(Volitelné)_ Nastavit setSiteSpeedSampleRate for increase of speed sample rate (https://goo.gl/FRHiAp) 
	- [ ] _(Volitelné)_ Nastavit event tracking (https://goo.gl/1xAgzO) 
	- [ ] _(Volitelné)_ Nastavit konverzní cíle
	- [ ] _(Volitelné)_ Omezit referral spam (http://mareklecian.cz/spamfilter/)
	- [ ] _(Volitelné)_ Aktivovat vyhledávání na stránce (přidání „s“)
	- [ ] _(Volitelné)_ Aktivovat on-site analytics (https://support.google.com/analytics/answer/2558867/?hl=cs)

## After Deploy

### WordPress
- [ ] Set unique keys and salts in wp-config.php
- [ ] Set FTP credentials in wp-config.php
- [ ] Set correct CHMOD for folders (e.g. uploads)
- [ ] Enable and set WP Super Cache
- [ ] Set up Akismet plugin if CF7 forms are used
- [ ] Test forms
- [ ] _(Optional)_ Add website/app to ManageWP

### Code
- [ ] Check validity of HTML with W3C validator

### Analytics, security and SEO
- [ ] Enable Security Headers
- [ ] Check robots meta is not set for noindex,nofollow on production
- [ ] Check Open Graph meta tags with Facebook debugger (https://developers.facebook.com/tools/debug/)
- [ ] Add website/app to Google Search Console
	- [ ] Add sitemap.xml
	- [ ] Connect Google Analytics and Search Console profiles (in Google Analytics)

### Search engines
- [ ] Add website to Seznam.cz (http://search.seznam.cz/pridej-stranku)

### Others
- [ ] Check if .env file is not accessible from the browser
- [ ] _(Optional)_ Add info page about privacy policy and cookies
- [ ] _(Optional)_ Redirect old URLs to new via 301
- [ ] _(Optional)_ Consider adding of `.well-known/security.txt`
- [ ] _(Optional)_ Add to Statusdroid monitoring
- [ ] _(Optional)_ Test Security Headers (https://securityheaders.com)
- [ ] Test the performance of website/app
	- [ ] Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- [ ] WebPagetest (http://www.webpagetest.org)
		- _Speed Index is best around 1000 pts. (on LTE), average 5000–10000, on "3G Slow" around 4 sec. is fine_
	- [ ] Lighthouse (https://web.dev/measure)
		- _First Meaningful Paint best up to 3 sec._
		- _First Interactive ideally low units of seconds_
		- _Perceptual Speed Index ideally up to 2000, max. 5 000_
		- _Time To First Byte ideally up to 500 ms_
