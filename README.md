# jQuery Accessible Carrousel using ARIA
jQuery Accessible Carrousel System, using <abbr title="Accessible Rich Internet Application">ARIA</abbr>
===========================
<p>This jQuery plugin will transform a simple list of <code>div</code>’s and <code>hx</code> into a <strong>fantastic-shiny carrousel system</strong>, using <abbr title="Accessible Rich Internet Application">ARIA</abbr>.</p>
===========================
```
&lt;div class="carrousel relative"&gt;      
  &lt;div class="carrousel__container mod--hidden" 
   data-carrousel-btn-previous-img="./arrow_back.png" 
   data-carrousel-btn-next-img="./arrow_next.png"
   data-carrousel-btn-previous-text="Show previous panel"
   data-carrousel-btn-next-text="Show next panel"
   data-carrousel-prefix-classes="news"
   data-carrousel-span-text-class="invisible"
   data-carrousel-transition="fade"
   data-carrousel-existing-hx="h3"&gt;
          
    &lt;div class="carrousel__content"&gt;
      &lt;h3&gt;A first panel&lt;/h3&gt;
      &lt;p&gt;Here the content.&lt;/p&gt;
    &lt;/div&gt;&lt;!--
 --&gt;&lt;div class="carrousel__content"&gt;
      &lt;h3&gt;A second panel&lt;/h3&gt;
      &lt;p&gt;Here the content.&lt;/p&gt;
    &lt;/div&gt;&lt;!--
 --&gt;&lt;div class="carrousel__content"&gt;
      &lt;h3&gt;A third panel&lt;/h3&gt;
      &lt;p&gt;Here the content.&lt;/p&gt;
    &lt;/div&gt;
          
  &lt;/div&gt;
&lt;/div&gt;
```

Keyboard navigation is supported, based on ARIA DP (http://www.w3.org/TR/2013/WD-wai-aria-practices-20130307/#tabpanel && http://www.oaa-accessibility.org/examplep/tabpanel1/):

__If you focus in the carrousel "buttons"__
- use Up/Left to see previous carrousel tab, 
- use Down/Right to see next carrousel tab
- Use "Home" to see first carrousel tab (wherever you are in tab buttons)
- Use "End" to see last carrousel tab (wherever you are in tab buttons)

__If you focus in a carrousel content__
- use Ctrl Up/left to Set focus on the carrousel button for the currently displayed carrousel tab
- use Ctrl PageUp to Set focus on the previous carrousel button for the currently displayed carrousel tab
- use Ctrl PageDown to Set focus on the next carrousel button for the currently displayed carrousel tab
 
__Warning__: Ctrl+PageUp/PageDown combination could activate for some browsers a switch of browser tabs. Nothing to do for this, as far as I know (if you have a solution, let me know).


A demo page is here: http://a11y.nicolas-hoffmann.net/carrousel/ 

It can be included for one, two carrousels systems or more in a page.

Enjoy.
