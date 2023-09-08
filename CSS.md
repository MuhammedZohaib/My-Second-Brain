
```css
:nth-child
*{} /*star selector*/
p{} /*elemnent selector*/
p,h1{} /*Group selector*/
#id{} /*id selector*/
.class{} /*class selector*/
/*attribute selectors*/
[attr=value]{} /*matches exact value*/
[attr~=value]{} /*value separated by whitespace*/
[attr$=value]{} /*ends with this value*/
[attr*=value]{} /*value as a substring*/
[attr^=value]{} /*begins with this value*/



/*specificity*/
0000 /*0 no.Of Ids  no.Of classes no.Of elements */

/*Group selectors*/
p h1{} /*Descendant selector*/
p > h1{} /*Child selector*/
p ~ h1 {} /*General sibling selector*/
p + h1 {} /*Adjacent sibling selctor*/

:hover
:visited
:active
:focus
:disabled
:enabled
:checked
:indeterminate
:valid
:invalid
:first-of-type
:last-of-type
:nth-of-type
:nth-last-of-type
:default
:fullscreen
:link /*all unvisited links*/
:empty /*all div elements with no children*/
/*psuedo-elements*/
::first-letter
::first-line
:required
::selection
::marker
::before
::after
::placeholder
/*order to follow*/
:link
:visited
:hover
:active
```

```text
Libraries
- pop motion
- 
```

```text/css
white-space: nowrap;
text-overflow: ellipsis | hidden | scroll;
writing-mode: vertical-rl;
word-wrap: ;
text-shadow: /*x y blur-radius shadow-color*/
```
