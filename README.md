# Deployment Checklist ☑️

Basic deployment checklist before WordPress deployment.

## .htaccess
- [ ] Force www redirection of website/app domain
- [ ] Set GZip compression and caching
- [ ] Activate SSL certificate and force redirect to HTTPS protocol
	- [ ] Make sure every asset is using the HTTPS protocol

## Code and assets
- [ ] Set meta tags (meta description, etc.)
	- [ ] Set Open Graph meta tags
- [ ] Mark key elements by WAI ARIA standards
- [ ] Check 404 error page
- [ ] _(Optional)_ Consider loading of alternative fonts via Web Font Loader (https://github.com/typekit/webfontloader)
- [ ] Check compiled CSS for unwated `@import`
- [ ] Set HTML code minification
- [ ] Consider lazyloading of images or/and iframes
- [ ] _(Optional)_ Consider setting JavaScript loading prioritization
- [ ] Optimize images in Optimage, TinyPNG, SVGOMG (or ImageOptim, ImageAlpha, Squoosh)
- [ ] Check the website/app in IE 11+ and other browsers

## WordPress before deploy
- [ ] Change admin password
- [ ] Remove or disallow access to readme.html and licence.txt files
- [ ] Review image sizes WordPress prints
- [ ] _(Optional)_ Consider setting auto update of plugins
- [ ] Check settings of forms if used

## Anayltics and SEO before deploy
- [ ] Add Google Analytics script
	- [ ] Activate demography report
	- [ ] Change length of data storage (Služba –> Údaje o měření –> Uchovávání dat)
	- [ ] _(Optional)_ Set setSiteSpeedSampleRate for increase of speed sample rate (https://goo.gl/FRHiAp) 
	- [ ] _(Optional)_ Set event tracking (https://goo.gl/1xAgzO) 
	- [ ] _(Optional)_ Set conversion goals
	- [ ] _(Optional)_ Limit referral spam (http://mareklecian.cz/spamfilter/)
	- [ ] _(Optional)_ Activate Site Search (add „s“)
	- [ ] _(Optional)_ Activate on-site analytics (https://support.google.com/analytics/answer/2558867/?hl=cs)
	- [ ] _(Optional)_ Add remarketing script (https://goo.gl/Qy7e81)

## WordPress after deploy
- [ ] Generate unique keys and salts for wp-config.php
- [ ] Set FTP credentials to wp-config.php
- [ ] Set correct CHMOD for folders (e.g. uploads)
- [ ] Add and setup WP Super Cache
- [ ] Set up Akismet plugin if CF7 forms are used
- [ ] _(Optional)_ Add website/app to ManageWP

## Code after deploy
- [ ] Check validity of HTML with W3C validator

## Analytics, security and SEO after deploy
- [ ] Enable Security Headers
- [ ] Check robots meta is not set for noindex,nofollow on production
- [ ] Check Open Graph meta tags with Facebook debugger (https://developers.facebook.com/tools/debug/)
- [ ] Add website/app to Google Search Console
	- [ ] Add sitemap.xml
	- [ ] Connect Google Analytics and Search Console profies (in Google Analytics)

## Search Engines
- [ ] Add website to Seznam.cz (http://search.seznam.cz/pridej-stranku)

## Others
- [ ] Check accessibility of .env file from the browser in case of using dotenv variables
- [ ] _(Optional)_ Consider adding an info page about privacy policy "Informace o zpracování osobních údajů/Jaké osobní údaje zpracováváme/Zásady zpracování osobních údajů" (e.g. to the footer, as a link to forms, etc. On every place, where website/app works with personal info)
- [ ] Test forms
- [ ] _(Optional)_ Redirect old URLs to new via 301 (only if was agreed with client)
- [ ] _(Optional)_ Consider dennying access to the authors page
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
