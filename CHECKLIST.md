# Deployment Checklist

## .htaccess
- [ ] **Force www redirection of web/app domain** (see KB)
- [ ] **Set GZip compression and caching** (see KB)
- [ ] **Activate SSL certificate and force redirect to HTTPS protocol** (see KB)
	- [ ] Make sure every URL a assets are using the HTTPS protocol

## Code and assets
- [ ] **Set meta tags (meta description, etc.)**
	- [ ] **Set Open Graph meta tags**
	- [ ] **Check Open Graph meta tags with Facebook debugger** (https://developers.facebook.com/tools/debug/)
- [ ] **Mark key elements by WAI ARIA standards** (see KB)
- [ ] **Check 404 error page**
- [ ] Consider loading of alternative fonts via Web Font Loader (https://github.com/typekit/webfontloader)
- [ ] **Check compiled CSS for unwated `@import`**
- [ ] **Set HTML code minification**
- [ ] **Check validity of HTML with W3C validator**
- [ ] Consider setting JavaScript loading prioritization (see Query KB)
- [ ] **Optimize images in ImageOptim, ImageAlpha, TinyPNG and SVGOMG**
- [ ] **Check the web/app in IE 11+ and other browsers**

## WordPress before deploy
- [ ] **Change admin password**
- [ ] **Remove or disallow access to readme.html and licence.txt files**
- [ ] Consider setting auto update of plugins
- [ ] **Check settings of forms if used**

## Anayltics and SEO before deploy
- [ ] **Check robots meta is not set for noindex, nofollow, nosnippet and noarchive**
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
- [ ] Add web/app to ManageWP

## Analytics and SEO after deploy
- [ ] **Add web/app to Google Search Console**
	- [ ] **Add sitemap.xml**
	- [ ] **Connect Google Analytics and Search Console profies (in Google Analytics)**

## Search Engines
- [ ] **Seznam** (http://search.seznam.cz/pridej-stranku)

## Others
- [ ] **Check accessibility of .env file from the browser in case of using dotenv variables**
- [ ] Consider adding an info page about privacy policy "Informace o zpracování osobních údajů/Jaké osobní údaje zpracováváme" (e.g. to the footer, as a link to forms, etc. On every place, where web/app works with personal info)
- [ ] Redirect old URLs to new via 301 (only if was agreed with client)
- [ ] Consider adding of `.well-known/security.txt`
- [ ] Add to Statusdroid monitoring
- [ ] **Test the performance of web/app**
	- [ ] Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- [ ] Google Mobile Friendly (https://search.google.com/search-console/mobile-friendly)
	- [ ] WebPagetest (http://www.webpagetest.org) *Speed Index best around 1000 pts. (on LTE), average 5000–10000*
	- [ ] Lighthouse (https://developers.google.com/web/tools/lighthouse/run)
        - *First Meaningful Paint best up to 3 sec.*
        - *First Interactive ideally low units of seconds*
        - *Perceptual Speed Index ideally up to 2000, max. 5 000*
	- [ ] Yellow Lab Tools (http://yellowlab.tools)
	- [ ] GTmetrix (https://gtmetrix.com)
