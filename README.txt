PUFFER POLO – WEBSITE FILES
===========================

What is in this folder
----------------------
index.html      The whole game: solo, two players on one keyboard, and online play.
peerjs.min.js   The library that connects two browsers for online play (PeerJS 1.5.5, MIT licence).
privacy.html    A privacy page template. Fill in the parts in [brackets].
ads.txt         A placeholder for the line your ad network gives you.
README.txt      This file.


1. Try it on your own computer
------------------------------
Double-click index.html. Solo and same-keyboard play work straight away.
To try online play by yourself, open index.html in two browser windows:
choose Online > Create game in one, then Online > type the code > Join in the other.


2. Put it on the internet
-------------------------
The site is plain files, so any static host works and no server is needed.
Easy free options: Netlify (app.netlify.com/drop – drag this folder onto the page),
Cloudflare Pages, or GitHub Pages. The site must be served over https, which all
three do for you.

You will want your own domain name (roughly US$10–15 a year). The host's settings
page walks you through connecting it. A domain you control matters for ads: AdSense
checks that you own the domain or can edit its content before it approves a site.


3. How online play works, and its limits
----------------------------------------
- The player who presses Create game is the host. Their browser runs the match and
  sends it to the guest; the guest's browser predicts its own movement so it still
  feels instant.
- The two browsers talk directly to each other. A free public service (the PeerJS
  cloud) introduces them, and relays the data if a direct link is impossible.
- That service is free and has no guarantees. If it is down, online play will not
  connect ("Could not reach the matchmaking service"). Solo play is unaffected.
  If the game gets busy, you can run your own copy of that service (search for
  "peerjs-server") and point the game at it by adding one line before the game's
  script in index.html, for example:
      <script>window.PEER_OPTS={host:"your-server.example.com",secure:true,path:"/"}</script>
- If the host closes or hides their tab, the match stops for both players.
- Because the host's browser runs the match, a determined host could cheat.
  That is fine for games between friends; ranked play would need a real server.
- To test with pretend lag, type  NET_LAG=80  in the browser console of both
  windows before connecting (80 ms each way).


4. Adding ads
-------------
The game has one ad slot built in, below the game. It is invisible until you fill it.

  a. Get your site live on your own domain and finish privacy.html.
  b. Apply to an ad network. For Google AdSense: adsense.google.com, add your site,
     and wait for review (days to a few weeks).
  c. Once approved, open index.html in a text editor and search for "ADS, STEP 1".
     Paste the loader script AdSense gives you where the comment says.
  d. Search for "ADS, STEP 2" and paste an ad unit into the slot.
  e. Put the line AdSense gives you into ads.txt.

Things to know before you rely on ad income:
  - A page that is only a game can be turned down for having too little content.
    The how-to-play text on the page helps; a few more real pages (about, tips,
    updates) help more.
  - Do not place ads beside the game or its buttons. Ad networks treat that as
    encouraging accidental clicks and can close the account. The built-in slot is
    kept clear of the controls for this reason. Never click your own ads.
  - Visitors from the EU, UK and Switzerland must be asked for consent through a
    Google-certified consent tool before personalised ads are shown. AdSense offers
    one in its "Privacy & messaging" section.
  - If the site is aimed at children under 13, stricter advertising and privacy
    rules apply in many countries. AdSense has a setting to mark a site as
    child-directed.
  - Full-screen ads between matches and "watch an ad for a reward" need a separate
    Google programme called H5 Games Ads, which you apply for once you own a games
    site. The game is not wired up for it yet.
  - Another route is submitting the game to a games portal (CrazyGames, Poki and
    similar). They run the ads and share the revenue, and each has its own
    requirements and code to add.

This is general information, not legal or financial advice.
