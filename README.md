# jQuery Accessible Carrousel using <abbr title="Accessible Rich Internet Application">ARIA</abbr>

<p>This jQuery plugin will transform a simple list of <code>div</code>’s and <code>hx</code> into a <strong>fantastic-shiny carrousel system</strong>, using <abbr title="Accessible Rich Internet Application">ARIA</abbr>.</p>

A full demo is here: https://a11y.nicolas-hoffmann.net/carrousel/


## Some informations


### A robust base

- This carrousel is based on simple <code>div</code>’s, so your page will be <strong>working even without JavaScript</strong>!
- The code that it produces is <strong>valid and semantic</strong>.
- It is entirely <strong>modular</strong>, quite easy to use and customise.

        	
### An accessible carrousel

- The order of navigation is <strong>simple and logical</strong>.
- You can easily <strong>navigate with the keyboard</strong> through it.
- It is based on <a href="http://www.w3.org/TR/2013/WD-wai-aria-practices-20130307/#tabpanel"><abbr title="Accessible Rich Internet Application">ARIA</abbr> Design Pattern for tabpanels</a>.
        	
### Lightweight

- 25<abbr title="kilobytes">kb</abbr> (development, readable by humans);
- 8<abbr title="kilobytes">kb</abbr> (minified, readable by machines);
- <strong>2<abbr title="kilobytes">kb</abbr> minified and gzipped</strong> (readable by… mutants&#8253;&#8253;).

### Free and no license problem

- No license problem: it uses <abbr title="Massachusetts Institute of Technology">MIT</abbr> license, so it’s <strong>free, open-source</strong> and you can do whatever you want with it, including commercial use. <a href="https://github.com/nico3333fr/jquery-accessible-carrousel-aria/blob/master/LICENSE">This permission notice</a> shall be included in all copies or substantial portions of it.
- However, it is not prohibited to send me a little “thanks”. ;)

### It’s (highly) customisable

- You can style it as you want;
- You can set up transitions… as you want;
- A lot of classes are proposed to customize it easily;
- There is no <abbr title="Cascading Style Sheet">CSS</abbr> code injected into <abbr title="HyperText Markup Language">HTML</abbr>, so your <abbr title="Document Object Model">DOM</abbr> is clean, especially for responsive.


===========================
## How it works

Basically:

- An ordered list ```ol class="js-carrousel__control__list"``` is inserted before all elements
- A div with a button is inserted between carrousel contents and the first control list. It is the “previous” button.
- Another one is inserted after all carrousel contents, for the… “next” button.
- Once the HTML markup is set up in a logical order for keyboard in the DOM, all ARIA attributes are added to make the link between tab buttons and tab contents, to know which one is related to which other.
- Keyboard shortcuts of ARIA Design Pattern for tabpanels are added, and you can easily navigate and use the carrousel.

===========================
## Keyboard

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
 
__New: if you focus on next/prev buttons__
- if you activate it, the focus will be put onto next/prev contents, not on control list.

__Warning__: Ctrl+PageUp/PageDown combination could activate for some browsers a switch of browser tabs. Nothing to do for this, as far as I know (if you have a solution, let me know).

===========================
## Demo

A demo page is here: https://a11y.nicolas-hoffmann.net/carrousel/ 

It can be included for one, two carrousels systems or more in a page.

===========================
## How to use it

You may use <code>npm i jquery-accessible-carrousel-aria</code>. Or download it.


```html
<div class="carrousel relative">      
  <div class="carrousel__container mod--hidden" 
   data-carrousel-btn-previous-img="./arrow_back.png" 
   data-carrousel-btn-next-img="./arrow_next.png"
   data-carrousel-btn-previous-text="Show previous panel"
   data-carrousel-btn-next-text="Show next panel"
   data-carrousel-prefix-classes="news"
   data-carrousel-span-text-class="invisible"
   data-carrousel-transition="fade"
   data-carrousel-existing-hx="h3">
          
    <div class="carrousel__content">
      <h3>A first panel</h3>
      <p>Here the content.</p>
    </div><!--
 --><div class="carrousel__content">
      <h3>A second panel</h3>
      <p>Here the content.</p>
    </div><!--
 --><div class="carrousel__content">
      <h3>A third panel</h3>
      <p>Here the content.</p>
    </div>
          
  </div>
</div>
```

<strong>Important note</strong>: for accessibility purposes (for VoiceOver), the plugin has to give focus to <code>hx</code> (<code>h2</code>, <code>h3</code>, <code>h4</code>, etc.) in tab contents. It is better having <code>hx</code> in each content tab.

- If you have some, it is great, you just have to tell the plugin. In the example above, you tell it via <code>data-carrousel-existing-hx</code>.<br /> And all these subtitles will be used in the <code>ol</code> list.
- If you don’t have, nevermind, just tell the plugin which level of <code>hx</code> to use with <code>data-carrousel-hx="hx"</code>, and it will insert an <code>h3 class="invisible"</code> for you in each tab panel (you can “visually” hide them if needed with <code>invisible</code> class). To specify the titles, use the attribute <code>data-carrousel-span-text="Panel"</code> and the plugin will create titles for each tab content: “Panel 1”, “Panel 2”, etc. And all these subtitles will be used in the <code>ol</code> list.
    
<strong>Other attributes are available:</strong>
    
- <code>data-carrousel-btn-previous-img</code>: the address of the image used for “previous” button.
- <code>data-carrousel-btn-previous-text</code>: the text of the “previous” button, will be put in the <code>alt</code> attribute if there is an image, and in the <code>title</code> attribute for the button.
- <code>data-carrousel-btn-next-img</code>: the address of the image used for “next” button.
- <code>data-carrousel-btn-next-text</code>: the text of the “next” button, will be put in the <code>alt</code> attribute if there is an image, and in the <code>title</code> attribute for the button.
- <code>data-carrousel-prefix-classes</code>: all the classes added for styling purpose will be prefixed, to simplify creating carrousel reusable styles.
- <code>data-carrousel-span-text-class</code>: in the <code>ol</code> list, the text will be wrapped into a <code>span</code> with this class. Example, <code>data-carrousel-span-text-class="yipikai"</code>: 
```<a … role="tab">
  <span class="yipikai">A robust base</span>
</a>```
- <code>data-carrousel-transition</code>: the value of this attribute will be added as a class on <code>div class="carrousel__container"</code>. And <abbr title="Cascading Style Sheet">CSS</abbr> will do the magic to animate it, for this page, I’ve created three transitions: “slide”, “fade” and “none”.




Enjoy.
