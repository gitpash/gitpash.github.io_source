---
title: break-out-game
layout: page
comments: true
author:
  name: Pavel Luzanov
  twitter: pavelluz
  # picture: /assets/images/johndoe.png
---
Building this simple BreakOut game followed by nice MDN instructions, the game is dead-simple but somehow help me to understand some canvas basics and simple UI interactions.


<html>
<head>
  <meta charset="utf-8"/>
  <title>2D Breakout Game</title>
  <style>
    .start-btn {
      display: flex;
      justify-content: center;
    }
    * { padding: 0; margin: 0; }
    canvas {  background: Bisque;
              display: block;
              margin: 0 auto;
            }
    @media screen and (max-width: 600px) {
    canvas {
      width: 400px;
      height: 250px;
      }
  }
  </style>
</head>
<body>
<div class="start-btn">
<input type="button" value="Start the Game" class="btn" />
</div>
<canvas id="gameCanvas" width="600" height="400"></canvas>

<script src="/assets/js/game.js">
</script>
</body>

{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://this-blog.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}