---
layout: post
title:  "Welcome to Jekyll!"
date:   2017-04-09 18:59:46 +0300
categories: jekyll update
read_time: true
display: draft
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:
<span class="icon icon--twitter">{% include icon-twitter.svg %}</span>
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}





Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
{% for image in site.static_files %}
  {% if image.path contains 'assets/images' %}

    <img src="{{site.baseurl}}{{image.path}}">
  {% endif %}
{% endfor %}

<html>
  <head>
    <title>Pythagorean Tree</title>
    <script>
      // функция рисует под углом angle линию из указанной точки длиной ln
      function drawLine(x, y, ln, angle) {
        context.moveTo(x, y);
        context.lineTo(Math.round(x + ln * Math.cos(angle)), Math.round(y - ln * Math.sin(angle)));
      }
      
      

// Функция рисует дерево
      function drawTree(x, y, ln, minLn, angle) {
        if (ln > minLn) {

          ln = ln * 0.71;
          drawLine(x, y, ln, angle);
          x = Math.round(x + ln * Math.cos(angle));
          y = Math.round(y - ln * Math.sin(angle));
          drawTree(x, y, ln, minLn, angle + Math.PI / 4);
          drawTree(x, y, ln, minLn, angle - Math.PI / 6);
          // если поставить угол Math.PI/4 , то выйдет классическое дерево
        }
      }
      // Инициализация переменных
      function init() {
        var canvas  = document.getElementById("tree"),
            x       = 100 + (canvas.width / 2),
            y       = 170 + canvas.height,  // положении ствола
            ln      = 120,                  // начальная длина линии
            minLn   = 5;                    // минимальная длина линии
        canvas.width  = 480; // Ширина холста
        canvas.height = 320; // высота холста
        context             = canvas.getContext('2d');
        context.fillStyle   = '#ddf'; // цвет фона
        context.strokeStyle = '#020'; //цвет линий
        context.fillRect(0, 0, canvas.width, canvas.height);
        context.lineWidth = 2; // ширина линий
        context.beginPath();
        drawTree(x, y, ln, minLn, Math.PI / 2);
        context.stroke();
      }
      
      window.onload = init;
      
    </script>
  </head>
  <body>
    <canvas id="tree"></canvas>
  
5% <input id="slide" type="range"
 min="5" max="200" step="5" value="100"/>200%
<br/>
  </body>
</html>

