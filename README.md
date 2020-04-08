# docsify-livere

LiveRe comment system for docsify.  [中文文档](taqini.space/2020/04/08/docsify-plugins)

>  LiveRe is an awesome comment system.

![](http://image.taqini.space/img/20200408223356.png)

## Feature of LiveRe

* Social Log-in
* Real time notification
* Comment quote
* Various statistic analysis
* Visitor search
* Keyword/ content search

## Demo

You can see the demo of docsify-livere [here](http://note.taqini.space/) 

The [demo](http://note.taqini.space/)  site has also installed another plugins [docsify-twemoji]()

![](http://image.taqini.space/img/20200408220415.png)



## Install

### Get your `data-uid`

If you've not have a livere account yet, click [here](livere.com/) to register.

You can got your `data-uid` in Code Managing page as following figure:

![](http://image.taqini.space/img/20200408213349.png)

### Configure index.html

Please include the following js code in the appropriate location on the `index.html`

```javascript
  window.$docsify = {
      plugins: [
        function (hook, vm) {
          // load livere
          hook.beforeEach(function(content) {
              var comment = "<div id='lv-container' data-id='city' data-uid='please_change_it'></div>\n\n----\n"
              return content + comment;
          });

          hook.doneEach(function() {
             (function(d, s) {
                 var j, e = d.getElementsByTagName(s)[0];
                 if (typeof LivereTower === 'function') { return; }
                 j = d.createElement(s);
                 j.src = 'https://cdn-city.livere.com/js/embed.dist.js';
                 j.async = true;
                 e.parentNode.insertBefore(j, e);
             })(document, 'script');
          });
        },
      ]
  }
```

And please replace `please_change_it` with your `data-uid`.

