# Installing Google Analytics in your website

Go to **Google Analytics > Admin > Tracking Info > Tracking Code** and get the tracking Code (GATC).

Example code:

```javascript
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-11111111-1', 'auto');
  ga('send', 'pageview');
</script>
```

Install the tracking code in your website, between `<head></head>` tags, in every page you want to track.

To do this you should access your website source code or contact with your webmaster.

Alternatively you can install Google Analytics via [Google Tag Manager](https://tagmanager.google.com). I personally recommend it that way because it will save you a lot of time in the future :)
