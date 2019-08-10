## .htaccess
- [ ] **Force www redirection of web/app domain** (see KB)
- [ ] **Set GZip compression and caching** (see KB)
- [ ] **Activate SSL certificate and force redirect to HTTPS protocol** (see KB)
	- [ ] Make sure every URL a assets are using the HTTPS protocol

## Code and assets
- [ ] **Set meta tags (meta description, etc.)**
	- [ ] **Set Open Graph meta tags**
- [ ] **Mark key elements by WAI ARIA standards** (see KB)
- [ ] **Check 404 error page**
- [ ] Consider loading of alternative fonts via Web Font Loader (https://github.com/typekit/webfontloader)
- [ ] **Check compiled CSS for unwated `@import`**
- [ ] **Set HTML code minification**
- [ ] Consider setting JavaScript loading prioritization (see KB)
- [ ] **Optimize images in Optimage, TinyPNG, SVGOMG (or ImageOptim, ImageAlpha, Squoosh)**
- [ ] **Check the web/app in IE 11+ and other browsers**
- [ ] **Generate critical CSS**

## WordPress before deploy
- [ ] **Change admin password**
- [ ] **Remove or disallow access to readme.html and licence.txt files**
- [ ] **Review image sizes WordPress prints**
- [ ] Consider setting auto update of plugins
- [ ] **Check settings of forms if used**

## Anayltics and SEO before deploy
- [ ] **Add Google Analytics script**
	- [ ] **Activate demography report**
	- [ ] **Change length of data storage (Služba –> Údaje o měření –> Uchovávání dat)**
	- [ ] Set setSiteSpeedSampleRate for increase of speed sample rate (https://goo.gl/FRHiAp)
	- [ ] Set event tracking (https://goo.gl/1xAgzO)
	- [ ] Nastav sledování cílů webu
	- [ ] Limit referral spam (http://mareklecian.cz/spamfilter/)
	- [ ] Activate Site Search (add „s“)
	- [ ] Activate on-site analytics (https://support.google.com/analytics/answer/2558867/?hl=cs)
	- [ ] Add remarketing script (https://goo.gl/Qy7e81)

## WordPress after deploy
- [ ] **Generate unique keys and salts for wp-config.php**
- [ ] **Set correct CHMOD for folders (e.g. uploads)**
- [ ] **Add and setup WP Super Cache**
- [ ] **Set up Akismet plugin if CF7 forms are used**
- [ ] Add web/app to ManageWP

## Code after deploy
- [ ] **Check validity of HTML with W3C validator**

## Analytics and SEO after deploy
- [ ] **Check robots meta is not set for noindex,nofollow on production**
- [ ] **Check Open Graph meta tags with Facebook debugger** (https://developers.facebook.com/tools/debug/)
- [ ] **Add web/app to Google Search Console**
	- [ ] **Add sitemap.xml**
	- [ ] **Connect Google Analytics and Search Console profies (in Google Analytics)**

## Search Engines
- [ ] **Add web to Seznam** (http://search.seznam.cz/pridej-stranku)

## Others
- [ ] **Check accessibility of .env file from the browser in case of using dotenv variables**
- [ ] Consider adding an info page about privacy policy "Informace o zpracování osobních údajů/Jaké osobní údaje zpracováváme/Zásady zpracování osobních údajů" (e.g. to the footer, as a link to forms, etc. On every place, where web/app works with personal info)
- [ ] Redirect old URLs to new via 301 (only if was agreed with client)
- [ ] Consider dennying access to the authors page
- [ ] Consider adding of `.well-known/security.txt`
- [ ] Add to Statusdroid monitoring
- [ ] **Test the performance of web/app**
	- [ ] Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- [ ] WebPagetest (http://www.webpagetest.org)
		- *Speed Index is best around 1000 pts. (on LTE), average 5000–10000, on "3G Slow" around 4 sec. is fine*
	- [ ] Lighthouse (https://web.dev/measure)
		- *First Meaningful Paint best up to 3 sec.*
		- *First Interactive ideally low units of seconds*
		- *Perceptual Speed Index ideally up to 2000, max. 5 000*
		- *Time To First Byte ideally up to 500 ms*

