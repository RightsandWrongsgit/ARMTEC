
# Some helpful HTML



### Abbreviations
If you tend to use a lot of jardon, the abbreviation tag is wonderful.
<abbr title="Better than sliced bread">BTSB</abbr>
and you can use it for all your favorite
<abbr title="Secret Code Jargon">SCJ</abbr>

### Highlighter
This html mark command is basically a <mark>highlighter</mark> of whatever is between its open and close.  It is default <mark>'yellow'</mark> in highlight color.
<br>
<br>

### Sub & Super Script
If you are writing out a chemistry equation you might want to subscript; or are you a superscript person?
<p>This text contains <sub>subscript</sub> text</p>
<p>This text contains <sup>superscript</sup> text</p>
&#x1D465;<sup>2</sup> - 3&#x1D465; - 28 = 0. Solve for &#x1D465;. <br />
<br />
H<sub>2</sub>SO<sub>4</sub> + NaOH &#8594; Na<sub>2</sub>SO<sub>4</sub> +
H<sub>2</sub>O
<br>
<br>
<br>

### Opening Details
<details>
  <summary>Open me!</summary>
  This is a demonstration of a disclosure widget.  You put in whatever narrative here and
  then when people click the summary triangle, this thing opens up to show the details.
</details>

<br>
<br>

### Quote me
Most of the time you would just edit stuff and change it.  But if you ever need to let someone know what <q>was</q> you can use...

### Strike Through
a strikethrough tag <s>around the old</s> and then show the new.
<br>
<br>

### List Group
Sometimes a list of items might better be presented in groups from an option select box. The code shown here works in a true HTML environment and can be confirmed on [CodePen](https://codepen.io/pietrobok/pen/OPMyJN). However, in the markup only GitHub pages is doesn't present full functionality for demo purposes here.

    <label for="countries">Choose a country:</label>
    <select name="country" id="countries">
    <option value="">--Please choose a country--
    </option>
    <optgroup label="North America">
      <option value="us">United States</option>
      <option value="ca">Canada</option>
    </optgroup>
    <optgroup label="Europe">
      <option value="uk">United Kingdom</option>
      <option value="fr">France</option>
    </optgroup>
  </select>

<br>
<br>

### Option Box
Or maybe at a more basic level you just need a form input box with a list of option values to select from...
<form>
  <label for="lang">Choose a language:</label>
  <input list="langs" name="lang" id="lang" />

  <datalist id="langs">
    <option value="English" />
    <option value="French" />
    <option value="Spanish" />
    <option value="Chinese" />
    <option value="German" />
  </datalist>
</form>

<br>
<br>


### Field Groups
If you have a bunch of fields you need on your form but they should be presented in logical groups you can do this...
<form>
  <fieldset>
    <legend>Name</legend>

    <label for="fname">First Name:</label>
    <input type="text" id="fname" name="fname" /><br />
    <label for="mname">Middle Name:</label>
    <input type="text" id="mname" name="mname" /><br />
    <label for="lname">Last Name:</label>
    <input type="text" id="lname" name="lname" />
  </fieldset>
  <br />
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" />
  <br /><br />
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" />
</form>






