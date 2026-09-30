# uBlockOrigin & uBlacklist Huge AI Blocklist
A huge blocklist of manually curated sites (1000+) that contain AI generated content, for the purposes of cleaning image search engines (Google Search, DuckDuckGo, and Bing) with uBlock Origin or uBlacklist. 

Also works on mobile ([iOS, iPadOS,](#iOS-iPadOS-Safari-only) [Android](#Android-via-Firefox)) via uBlacklist, as well as pihole/adguard (via [Hosts file](#hosts-file-for-pi-holeadguard))

## PC/Desktop installation

### Installing it with uBlock Origin

**One-click import (any platform)**

If you have uBlock Origin installed, click [this link](https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FCallenDV%2FuBlockOrigin-HUGE-AI-Blocklist%2Fmain%2Flist.txt&title=Sites%20using%20AI%20generated%20content) to import the filter list in just a click! Quick and simple.

**Manual Import**

1. Make sure that you have the uBlock Origin Extension for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/), [Chrome](https://chromewebstore.google.com/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm), or any browser that supports uBlock Origin

2. Click on the uBlock Origin Extension, and in the bottom right, there is a cog-wheel symbol--named the dashboard. Click it.

3. Once you are in the dashboard, look towards the top. Click on the tab that says "Filter lists".

4. Look towards the bottom, and expand the ```Import``` button.

5. Copy and paste this URL into the dialogue box: 
```
https://raw.githubusercontent.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/main/list.txt
```

6. Apply changes, and you're set!

<details>
<summary>Here's a video guide on how to do this (click the dropdown to expand) </summary>
<br>

https://github.com/user-attachments/assets/c379a750-53eb-4813-8cea-757f34ab5a2d

</details>

> [!TIP]
> uBlock Origin will automatically refresh the filter list once a day, so you'll always have up-to-date filters.
> If you want to force an update of the filter list, pressing the stopwatch next to the newly added list, then pressing ```Update now``` will achieve that.


> [!IMPORTANT]
> If you find that your imported list isn't working, it may be due to an outdated web browsing session. If you haven't restarted your web browser for a long time, there's a chance the session won't update how it should, meaning importing the list into uBlock Origin or uBlacklist won't function correctly. Try creating a new session by closing <ins>**all**</ins> web browser windows, waiting until all processes are fully closed (4-5 second wait), then re-opening your web browser. That should help; if not, then try clearing your browser's cache.

### Android (via Firefox)

<details>
<summary>Installation for uBlock Origin (expand) </summary>
<br>

  **One-click import**

If you have uBlock Origin installed, click [this link](https://subscribe.adblockplus.org?location=https%3A%2F%2Fraw.githubusercontent.com%2FCallenDV%2FuBlockOrigin-HUGE-AI-Blocklist%2Fmain%2Flist.txt&title=Sites%20using%20AI%20generated%20content) to import the filter list in just a click! Quick and simple.

**Manual Import**

1. Make sure that you have the uBlock Origin Extension for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/).

2. Hit the three dots in the top right, and hit the Extensions button.

3. Click on the uBlock Origin Extension, and in the bottom right, there is a cog-wheel symbol--named the dashboard. Click it.

4. Once you are in the dashboard, look towards the top. Click on the tab that says `Filter lists`.

5. Look towards the bottom, and expand the ```Import``` button.

6. Copy and paste this URL into the dialogue box: 
```
https://raw.githubusercontent.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/main/list.txt
```

6. Apply changes, and you're set!
</details>

## Hosts file for pi-hole/adguard/NextDNS

I've added a list in HOSTS format for pi-hole/adguard/NextDNS or for use in your own operating system's hosts file.

```
https://raw.githubusercontent.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/main/noai_hosts.txt
```

For use in your operating system, visit the url and copy-paste the contents inside your operating systems hosts file. 

Here's a simple guide on how to [access your hosts file on Linux, macOS, and Windows.](https://linuxize.com/post/how-to-edit-your-hosts-file/)

### For pi-hole: 
1. Visit your admin's dashboard
2. Click on `Adlists`
3. Copy and paste the url into the `address:` box
4. Hit the `add` button, and it should be added.

### For Adguard:

1. Open Adguard Home Dashboard
2. Go to filters --> DNS blocklists.
3. Click `Add blocklist`, then `Add a custom list`.
4. Enter the name of the list (eg. AI blocklist) into the first dialogue box.
5. Copy and paste the url into the second dialogue box.
6. Hit save, and the list is added!

### For NextDNS:

Unfortunately, since NextDNS doesn't yet support list imports, all entries will have to be manually typed in.

1. Open NextDNS Dashboard
2. Go to Denylist
3. Focus the domain input box
4. Copy and paste the url into the box
5. Hit enter
6. Repeat 3-5 until list is completed

## Additional lists

Currently, there are two lists: The [main](github.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/blob/main/list.txt) default list, and the [nuclear](github.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/blob/main/additional_list_nuclear.txt) list.

The nuclear list has sites that contain a mix of authentic and AI generated imagery (eg. DeviantArt, Artstation, Stock Photography sites, etc), which make it tricky to outright block in the main filter list, so I've designated it to a separate list that you can toggle on and off if you so desire.


<details>
<summary>uBlock Origin Nuclear List (expand) </summary>
<br>

```
https://raw.githubusercontent.com/CallenDV/uBlockOrigin-HUGE-AI-Blocklist/main/additional_list_nuclear.txt
```

</details>


## Allowlisting sites
Don't like a certain site being blocked? You can easily create an allowlist in your own personal uBlock Origin or uBlacklist filter list. 

Here's how to do it. 

<details>
<summary>Steps for uBlock Origin (expand) </summary>
<br>

1. Toggle the [DOM inspector](https://github.com/gorhill/uBlock/wiki/DOM-inspector) `</>` through uBlock Origin's [logger](https://github.com/gorhill/uBlock/wiki/The-logger).
2. Locate the URL you want to allowlist.
3. Click on the filter you want to disable (eg. vecteezy.com); it should then be crossed out.
4. Press the save icon, then the "Create" button.

Boom! Now it's allowlisted!

Or, if you don't want to go through that mumbo-jumbo, add this line in your filter list: 
```
#@#a[href*="example.com"]:upward(li):remove()
```

Change "example.com" to the URL you want to allowlist. Copy & paste that in uBlock Origin's "My filters" list, and you're set!

</details>


## Extended Filtering

It is possible to filter AI results based on keywords. It was originally in the list, but it's been taken out to make it configurable and/or optional.

### uBlock Origin
In your personal filter list, you can use this template to add your own keywords you would like to block.

```
google.com,duckduckgo.com,bing.com##div>a:has-text(/Your Text Here/i):upward(div):style(opacity:0!important)
```
Replace "Your Text Here" with your preferred keywords. A short list of **optional** procedural filters that you can use for uBlock Origin are listed in a dropdown below:

<details>
<summary> Optional procedural filters for uBlock Origin </summary>
<br>

```
google.com,duckduckgo.com,bing.com##div>a:has-text(/Stable Diffusion/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/AI Art/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/Generative AI/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/Ai/):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/AI/):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/Lora Model/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/diffusion/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/midjourney/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/niji/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/SDXL/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/ai generated/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/aiart/i):upward(div):style(opacity:0!important)
google.com,duckduckgo.com,bing.com##div>a:has-text(/AI illustration/i):upward(div):style(opacity:0!important)
```

</details>
  
## Contributing
If you'd like to contribute to the list, feel free to clone this repo and create a pull request for the site(s) you'd like to add to the list. Make sure to update all files (including hosts file) wherever necesessary (except the nuclear list if you want the site to appear in the main list of course).

If you don't know how to do that or don't want to, you can instead create an issue of the site that you'd like to be included in the list, wherein I'd look over it and add it in myself. Any way that you contribute is greatly appreciated!

## To Do
- [x] Provide blocklist for uBlacklist compatibility

- [x] Blocklist functionality on DuckDuckGo and Bing (ew)

- [x] Create hosts file for pi-hole/adguard

- [ ] Startpage, Ecosia, Brave support (for uBlock Origin)

## Happy Pride Month!
LGBTQ+ Rights! 🏳️‍🌈🏳️‍⚧️

## Special Thanks

Special thanks to: 

+ This [pastebin](https://pastebin.com/B8kP4imQ) (since it added even more sites to my blocklist)

+ u/AchernarB for the [awesome snip-bit of code.](https://www.reddit.com/r/uBlockOrigin/comments/13uyex5/how_to_block_results_from_a_specific_site_in_the/)

+ Raymond Hill, [uBlock Origin extension](https://github.com/gorhill/uBlock)

## Related Projects

[Super SEO Spam Suppressor (SSSS)](https://github.com/NotaInutilis/Super-SEO-Spam-Suppressor) by NotaInutilis

> An anticapitalist blocklist targeting websites abusing SEO tactics to spam web searches with data pollution and security risks: content farms, scrapers, copycats, generative AI, scams, advertisements, malwares, and useless wasteful garbage in general. It is best used with uBlacklist. 

[Blocklist for AI Music on Youtube](https://surasshu.com/blocklist-for-ai-music-on-youtube/) by surasshu

> A blocklist that targets AI music channels on YouTube, through the use of the Blocktube extension.

[Journey Buster 3](https://journeybuster.com/) by k0vac

> A Chromium extension that lets you know if an image is AI generated, for use on Twitter.

[Awesome List of uBlacklist Subscriptions](https://github.com/rjaus/awesome-ublacklist) by rjaus

> A compilation of awesome uBlacklist subscriptions to block various sites from appearing in Google, Bing, or DuckDuckGo search.

[Anti-AI Google Search Tips](https://github.com/laylavish/TipsTricksGoogleSearch) by yours truly

> Tips and tricks to make Google Search (and other search engines that have similar operators) return authentic imagery.
