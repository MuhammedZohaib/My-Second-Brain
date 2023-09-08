```html
<!--The header of a content section or the web page. The web page header often contains the website branding or logo.-->
<header> 
<!--The navigation links of a section or the web page.-->
<nav>
<!--The footer of a content section or the web page. On a web page, it often contains secondary links, the copyright notice, privacy policy and cookie policy links.-->
<footer>
<!--Specifies the main content of a section or the web page.-->
<main>
<!--A secondary set of content that is not required to understand the main content.-->
<aside>
<!--An independent, self-contained block of content such as a blog post or product.-->
<article>
<!--A standalone section of the document that is often used within the body and article elements.-->
<section>
<!--A collapsed section of content that can be expanded if the user wishes to view it.-->
<detail>
<!--Specifies the summary or caption of a <details> element.-->
<summary>
<!--Headings on the web page. <h1> indicates the most important heading whereas <h6> indicates the least important.-->
<h1><h2><h3><h4><h5><h6>
<!--Used to describe a quotation.-->
<blockquote>
<!--Used to define a description for the preceding <dt> element.-->
<dd>
<!--Used to define a description list.-->
<dl>
<!--Used to describe terms inside <dl> elements.-->
<dt>
<!--Defines a caption for a photo image.-->
<figcaption>
<!--Applies markup to a photo image.-->
<figure>
<!--Adds a horizontal line to the parent element.-->
<hr>
<!--Used to define an item within a list.-->
<li>
<!--A semantic alternative to <ul> tag.-->
<menu>
<!--Defines an ordered list.-->
<ol>
<!--Defines a paragraph.-->
<p>
<!--Used to represent preformatted text. Typically rendered in the web browser using a monospace font.-->
<pre>
<!--Unordered list-->
<ul>
<!--An anchor link to another HTML document.-->
<a>
<!--Specifies that the containing text is an abbreviation or acronym.-->
<abbr>
<!--Bolds the containing text. When used to indicate importance use <strong> instead.-->
<b>
<!--A line break. Moves the subsequent text to a new line.-->
<br>
<!--Defines the title of creative work (for example a book, poem, song, movie, painting or sculpture). The text in the <cite> element is usually rendered in italics.-->
<cite>
<!--Indicates that the containing text is a block of computer code.-->
<code>
<!--Indicates machine-readable data.-->
<data>
<!--Emphasizes the containing text.-->
<em>
<!--The containing text is displayed in italics. Used to indicate idiomatic text or technical terms.-->
<i>
<!--The containing text should be marked or highlighted.-->
<mark>
<!--The containing text is a short quotation.-->
<q>
<!--Displays the containing text with a strikethrough or line through it.-->
<s>
<!--The containing text represents a sample.-->
<samp>
<!--Used to represent small text, such as copyright and legal text.-->
<small>
<!--A generic element for grouping content for CSS styling.-->
<span>
<!--Displays the containing text in bold. Used to indicate importance.-->
<strong>
<!--The containing text is subscript text, displayed with a lowered baseline.-->
<sub>
<!--The containing text is superscript text, displayed with a raised baseline.-->
<sup>
<!--A semantic tag used to display both dates and times.-->
<time>
<!--Displays the containing text with a solid underline.-->
<u>
<!--The containing text is a variable in a mathematical expression.-->
<var>
<!--Used to embed audio in web pages.-->
<audio>
<!--Used to render 2D and 3D graphics on web pages.-->
<canvas>
<!--Used as a containing element for external content provided by an external application such as a media player or plug-in application.-->
<embed>
<!--Used to embed a nested web page.-->
<iframe>
<!--Embeds an image on a web page.-->
<img>
<!--Similar to <embed> but the content is provided by a web browser plug-in.-->
<object>
<!--An element that contains one <img> element and one or more <source> elements to offer alternative images for different displays/devices.-->
<picture>
<!--Embeds a video on a web page.-->
<video>
<!--Specifies media resources for <picture>, <audio> and<video> elements.-->
<source>
<!--Used to define Scalable Vector Graphics within a web page.-->
<svg>
<!--Defines a table element to display table data within a web page.-->
<table>
<!--Represents the header content of a table. Typically contains one <tr> element.-->
<thead>
<!--Represents the main content of a table. Contains one or more <tr>elements.-->
<tbody>
<!--Represents the footer content of a table. Typically contains one <tr> element.-->
<tfoot>
<!--Represents a row in a table. Contains one or more <td> elements when used within <tbody> or <tfoot>. When used within <thead>, contains one or more <th> elements.-->
<tr>
<!--Represents a cell in a table. Contains the text content of the cell.-->
<td>
<!--Defines a header cell of a table. Contains the text content of the header.-->
<th>
<!--Defines the caption of a table element.-->
<caption>
<!--Defines a semantic group of one or more columns in a table for formatting.-->
<colgroup>
<!--Defines a semantic column in a table.-->
<col>
```

```html
<!DOCTYPE html>

<html lang="en">
	<head>
		<title></title>
	<head>
	<body>
		<header>
		</header>
		<nav>
			<menu>
		</nav>
		<main>
			<article>
			<aside>
			<section>
		</main>
		<footer>
			<nav>
			<nav>
		</footer>
	</body>
</html>

```

```html
<!--Metadata-->
<meta name="author" content="Muhammad Zohaib">
<meta name="description" content="Description about the website">
<meta name="keywords" content="SEO Keywords"> <!--Do not use now-->
<meta name="robots" content="index, follow"> <!--index follow noindex nofollow-->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name=”title”/>
<meta name="language" content="english">
<meta name="googlebot" content=”notranslate” />
<meta name="revised" content="Sunday, July 18th, 2010, 5:15 pm" />
<meta name="rating" content="safe for kids">
<meta name="copyright" content="Copyright 2022">
<meta http-equiv="content-type" content="text/html">
<meta http-equiv="default-style"/>
<meta http-equiv="refresh"/>
<meta http-equiv=”Content-language”/>
<meta http-equiv="Cache-Control" content="no-cache">
<meta name="format-detection" content="telephone=yes"/>
<meta name="HandheldFriendly" content="true"/>
```

```html
<!--Open Graph Protocol-->
<!--Also uses meta tags but instead of name attribute they use property attribute. Each value in the property tag starts with og: as convention-->
<!--first four tags are must-->

<meta property="og:title" content="Page title"/>
<meta property="og:type" content="website"/>
<meta property="og:url" content="Page title"/>
<meta property="og:image" content="Page title"/>
<meta property="og:description" content="Page title"/>
<meta property="og:locale" content="en_US"/>
<meta property="og:site_name" content="Zohaib's Website"/>


<!--twitter card-->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:site" content="@digitalocean" />
<meta name="twitter:title" content="Sammy the Shark" />
<meta name="twitter:description" content="Senior Selachimorpha at DigitalOcean" />
<meta name="twitter:image" content="https://html.sammy-codes.com/images/large-profile.jpg" />

<!-- Non-Essential, But Required for Analytics -->
<meta property="fb:app_id" content="your_app_id" />
<meta name="twitter:site" content="@website-username">

```

```html

<figure>
	<img src="">
	<figcaption><figcaption>
<figure>
```

## Forms and Validations

There are two types of validations:

- Client-Side Validations
- Server-Side Validations

```html
<input type="text" required minlength=3 maxlength=12
```

```css
input:focus:invalid{
	border: 1px solid red;
}
```


```html
<form>
	<fieldset id="group1">
		<label>
		<input type="radio" name="group1"> Option1
		</label>
		<label>
		<input type="radio" name="group1"> Option2
		</label>
		<label>
		<input type="radio" name="group1"> Option3
		</label>
	</fieldset>

</form>
```

```c
required
//text
maxlength
minlength
pattern
//number range
min
max
//file
multiple
```

```
//supported video types by most browsers
.mp4
.webm
.ogg

//supported audio types by most browsers
.mp3
.wav
.ogg

//supported image tags by most browsers
.apng
.avif
.gif
.jpeg
.png
.svg
.webp
```

```html
<video>
	<source src="address to a video file" type="video/mp4">
</video>

<audio>
	<source src="address to a audio file" type="audio/mpeg">
</audio>
```

```html
<iframe src="" allow="camera 'none'; microphone 'none'" sandbox="" ></iframe>

<!--Sandbox Attributes-->
allow = "fullscreen"
allow = "geolocation"
allow = "camera, microphone"
allow = "allow-downloads allow-forms allow-modals allow-oreintational-lock"
allow = "allow-popups allow-presentation allow scripts"





```