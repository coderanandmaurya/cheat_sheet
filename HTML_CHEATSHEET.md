### Basic HTML Structure

**`<!DOCTYPE html>`**
- **Use**: Declares the document type and version of HTML. Always place this at the top of your HTML document.
```html
<!DOCTYPE html>
```

**`<html>`**
- **Use**: The root element of an HTML document. All other elements are nested inside it.
```html
<html lang="en">
    <!-- Head and body elements go here -->
</html>
```

**`<head>`**
- **Use**: Contains metadata and links to external resources. Place it within the `<html>` tag.
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Title</title>
</head>
```

**`<meta charset="UTF-8">`**
- **Use**: Specifies character encoding. Essential for proper text display.
```html
<meta charset="UTF-8">
```

**`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**
- **Use**: Ensures proper rendering and scaling on mobile devices.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

**`<title>`**
- **Use**: Sets the page title, which appears in the browser tab.
```html
<title>Document Title</title>
```

**`<body>`**
- **Use**: Contains all the visible content of the page.
```html
<body>
    <!-- Visible content goes here -->
</body>
```

### Common HTML Elements

**Headings (`<h1>` to `<h6>`)**
- **Use**: Structure content hierarchically. `<h1>` is the highest level, `<h6>` is the lowest.
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
```

**Paragraphs (`<p>`)**
- **Use**: Wrap text into paragraphs.
```html
<p>This is a paragraph of text.</p>
```

**Links (`<a>`)**
- **Use**: Create hyperlinks to other pages or email addresses.
```html
<a href="https://www.example.com">Visit Example</a>
<a href="mailto:someone@example.com">Send Email</a>
```

**Images (`<img>`)**
- **Use**: Embed images. Always include the `alt` attribute for accessibility.
```html
<img src="image.jpg" alt="Description of image">
```

**Lists**

**Unordered List (`<ul>`)**
- **Use**: Display a list of items with bullet points.
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

**Ordered List (`<ol>`)**
- **Use**: Display a list of items with numbers.
```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

**Tables**
- **Use**: Present tabular data. Use `<thead>`, `<tbody>`, and `<tfoot>` to organize rows and columns.
```html
<table>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
        <tr>
            <td>Data 3</td>
            <td>Data 4</td>
        </tr>
    </tbody>
</table>
```

**Forms**
- **Use**: Collect user input. Include `<form>`, `<label>`, `<input>`, and `<button>`.
```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">

    <label for="email">Email:</label>
    <input type="email" id="email" name="email">

    <button type="submit">Submit</button>
</form>
```

**Div (`<div>`)**
- **Use**: Group block-level elements and apply styles or layout.
```html
<div>
    <p>This is a block-level element.</p>
</div>
```

**Span (`<span>`)**
- **Use**: Group inline elements and apply styles.
```html
<p>This is a <span style="color: red;">highlighted text</span> within a paragraph.</p>
```

### Semantics Elements

**`<header>`**
- **Use**: Define introductory content or navigation links for a section or page.
```html
<header>
    <h1>Welcome to My Website</h1>
    <nav>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
</header>
```

**`<main>`**
- **Use**: Identify the main content of the document. Use only one `<main>` element per page.
```html
<main>
    <article>
        <h2>Article Title</h2>
        <p>Content of the article goes here.</p>
    </article>
</main>
```

**`<article>`**
- **Use**: Represent a self-contained piece of content that can be distributed independently.
```html
<article>
    <h2>Article Title</h2>
    <p>This is a self-contained piece of content, like a news article or blog post.</p>
</article>
```

**`<footer>`**
- **Use**: Define footer content such as copyright info, contact details, or additional links.
```html
<footer>
    <p>© 2024 My Website. All rights reserved.</p>
</footer>
```

### HTML5 New Elements

**`<aside>`**
- **Use**: Represent content tangentially related to the content around it, like sidebars.
```html
<aside>
    <h3>Related Information</h3>
    <p>This section contains additional information related to the main content.</p>
</aside>
```

**`<figure>`**
- **Use**: Group media content like images, diagrams, or code snippets. Often includes a `<figcaption>` for a caption.
```html
<figure>
    <img src="image.jpg" alt="Description of image">
    <figcaption>This is a caption for the image.</figcaption>
</figure>
```

**`<figcaption>`**
- **Use**: Provide a caption for content within a `<figure>`.
```html
<figure>
    <img src="image.jpg" alt="Description of image">
    <figcaption>This is a caption for the image.</figcaption>
</figure>
```

**`<section>`**
- **Use**: Define thematic groups of content, typically with a heading. Helps in organizing content logically.
```html
<section>
    <h2>Section Title</h2>
    <p>Content for this section goes here.</p>
</section>
```
