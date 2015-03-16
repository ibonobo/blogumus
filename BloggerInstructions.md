# Introduction #

A couple of years ago, Roy Tanck released his famous WP Cumulus plugin which was then adapted for Blogger blogs. At first it was hosted by him, then, when that was no longer available, various bloggers started to host it themselves, mostly on Google Pages. When that service became Google Sites, some bloggers lost access to the code. We are presenting it here hopefully in a more permanent format.


# Details #

To install it in your blog, sign in to your [Dashboard](http://www.blogger.com/home). Click on the **Design** link for your blog, then **Edit HTML**. As with any template modification, prior to modifying your template you should click **Download Full Template** and save a backup copy somewhere so that you can backtrack in case you make a mistake. Before committing any changes to the template, you might want to click **Preview** (though this is not always accurate). If something is wrong, you can revert to the last saved template with **Clear Edits**.

Search for 

&lt;b:section class='sidebar' id='sidebar' preferred='yes'&gt;

_or, if you cannot find for part of it, such as_<b:section class='sidebar'_(in most browsers pressing Ctrl + F brings up a search box; click inside the text box before searching, so that the browser focus changes appropriately)._

## Code ##
Immediately after the section header, copy and paste the following block of code:
```
<b:widget id='Label99' locked='false' title='Labels' type='Label'>
<b:includable id='main'>
<b:if cond='data:title'>
<h2><data:title/></h2>
</b:if>
<div class='widget-content'>
<script src='http://blogumus.googlecode.com/files/tagcloud.swf' type='text/javascript'/>
<div id='flashcontent'>Blogumus by <a href="http://3w.blogidol.ro">BlogIdol</a> after Roy Tanck and Amanda Fazani</div>
<script type='text/javascript'>
var so = new SWFObject(&quot;http://blogumus.googlecode.com/files/swfobject.js&quot;, &quot;tagcloud&quot;, &quot;240&quot;, &quot;300&quot;, &quot;7&quot;, &quot;#ffffff&quot;);
// uncomment next line to enable transparency
//so.addParam(&quot;wmode&quot;, &quot;transparent&quot;);
so.addVariable(&quot;tcolor&quot;, &quot;0x333333&quot;);
so.addVariable(&quot;mode&quot;, &quot;tags&quot;);
so.addVariable(&quot;distr&quot;, &quot;true&quot;);
so.addVariable(&quot;tspeed&quot;, &quot;100&quot;);
so.addVariable(&quot;tagcloud&quot;, &quot;<tags><b:loop values='data:labels' var='label'><a expr:href='data:label.url' style='12'><data:label.name/></a></b:loop></tags>&quot;);
so.addParam(&quot;allowScriptAccess&quot;, &quot;always&quot;);
so.write(&quot;flashcontent&quot;);
</script>
<b:include name='quickedit'/>
</div>
</b:includable>
</b:widget>
```

Save your template, or simply modify the code as explained below even before the first preview.


## Customization ##

Further customization can be achieved by changing the following variables in the code above:
  * **240** and **300** are width and height pixels; adapt it to the size of your column after measuring with a pixel ruler.
  * **ffffff** is the background color in hex; you can find it by inspecting your template or by "stealing" it with an imaging tool.
  * **333333** is the text color.
  * **100** is the animation speed.
  * **12** is the text size

Feel free to experiment with various values until you find something that suits you.


# Other copies #

The [.js](http://sites.google.com/site/bloggerustemplatus/code/swfobject.js) file and [.swf](http://sites.google.com/site/bloggerustemplatus/code/tagcloud.swf) can also be found at alternate locations with simple [JS](http://www.google.com/search?q=swfobject.js) or [SWF](http://www.google.com/search?q=tagcloud.swf) Google searches.
A similar Google Code Project is [Blogumulus](http://code.google.com/p/blogumulus) containing many other scripts.