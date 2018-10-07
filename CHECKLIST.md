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
- [ ] **Check , že není zakázáno indexování a procházení robotů skrz meta noindex, nofollow, nosnippet a noarchive jako pozůstatek z dev prostředí**
- [ ] **Nasaď měřící skript Google Analytics**
	- [ ] **Activate demography report**
	- [ ] **Nastav délku uchování dat (Služba –> Údaje o měření –> Uchovávání dat)**
	- [ ] Nastav setSiteSpeedSampleRate pro zvýšení vzorků pro testování rychlosti (https://goo.gl/FRHiAp)
	- [ ] Nastav sledování událostí – event tracking (https://goo.gl/1xAgzO)
	- [ ] Nastav sledování cílů webu
	- [ ] Nastav omezení referral spamu (http://mareklecian.cz/spamfilter/)
	- [ ] Aktivuj Site Search (přidat „s“)
	- [ ] Aktivuj Analýzy na stránce (https://support.google.com/analytics/answer/2558867/?hl=cs)
	- [ ] Doplň kód o remarketing skript (https://goo.gl/Qy7e81)

## WordPress after deploy
- [ ] **Vygeneruj unikátní extra keys a salts ve wp-config.php**
- [ ] **Nastav správných CHMOD práv adresářům (např. uploads)**
- [ ] **Nasaď WP Super Cache**
- [ ] Přidej web/aplikaci do konzole ManageWP (pouze u supportovaných projektů)

## Analytics and SEO after deploy
- [ ] **Registruj web/aplikaci do Google Search Console**
	- [ ] **Podstrč sitemap.xml**
	- [ ] **Propoj Google Analytics a Search Console profilů (na straně GA)**

## Search Engines
- [ ] **Seznam** (http://search.seznam.cz/pridej-stranku)

## Others
- [ ] **Check accessibility of .env file from the browser in case of using dotenv variables**
- [ ] Zvaž přidání informační stránky "Informace o zpracování osobních údajů/Jaké osobní údaje zpracováváme" (např. do patičky, jako odkaz k formulářům, atp. na všechna místa, kde se s os. údaji pracuje)
- [ ] Směruj starých URL na nové přes kód 301 (pokud bylo dohodnuto s klientem)
- [ ] Zváž přidání souboru `.well-known/security.txt`
- [ ] Přidej do monitoringu Statusdroid
- [ ] **Otestuj performance webu**
	- [ ] Google PageSpeed Insights (https://developers.google.com/speed/pagespeed/insights/)
	- [ ] Google Mobile Friendly (https://search.google.com/search-console/mobile-friendly)
	- [ ] WebPagetest (http://www.webpagetest.org) *Speed Index ideálně kolem 1000 (na LTE), průměr 5000–10000*
	- [ ] Lighthouse (https://developers.google.com/web/tools/lighthouse/run)
        - *First Meaningful Paint ideálně do 3 vteřin*
        - *First Interactive ideálně nízké jednotky vteřin*
        - *Perceptual Speed Index ideálně do 2000, nejvíce 5 000*
	- [ ] Yellow Lab Tools (http://yellowlab.tools)
	- [ ] GTmetrix (https://gtmetrix.com)
