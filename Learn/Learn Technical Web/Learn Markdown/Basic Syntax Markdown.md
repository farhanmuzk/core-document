# Panduan Lengkap Sintaks Markdown

Dokuementasi pembelajaran saya tentang Markdown

---
## 1. **Heading**

Gunakan `#` untuk membuat heading.  
Semakin banyak `#`, semakin kecil ukuran heading.

```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---
## 2. **Emphasis**

You can add emphasis by making text bold or italic.

### Bold[](https://www.markdownguide.org/basic-syntax/#bold)

To bold text, add two asterisks or underscores before and after a word or phrase. To bold the middle of a word for emphasis, add two asterisks without spaces around the letters.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`I just love **bold text**.`|`I just love <strong>bold text</strong>.`|I just love **bold text**.|
|`I just love __bold text__.`|`I just love <strong>bold text</strong>.`|I just love **bold text**.|
|`Love**is**bold`|`Love<strong>is</strong>bold`|Love**is**bold|
### Italic[](https://www.markdownguide.org/basic-syntax/#italic)

To italicize text, add one asterisk or underscore before and after a word or phrase. To italicize the middle of a word for emphasis, add one asterisk without spaces around the letters.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`Italicized text is the *cat's meow*.`|`Italicized text is the <em>cat's meow</em>.`|Italicized text is the _cat’s meow_.|
|`Italicized text is the _cat's meow_.`|`Italicized text is the <em>cat's meow</em>.`|Italicized text is the _cat’s meow_.|
|`A*cat*meow`|`A<em>cat</em>meow`|A_cat_meow|
### Strikethrough[](https://www.markdownguide.org/basic-syntax/#strikethrough)

To strike through text, add two tilde symbols (`~`) before and after a word or phrase.

|Markdown|HTML|Rendered Output|
|---|---|---|
|`This is ~~struck through~~ text.`|`<del>This is struck through text.</del>`|This is ~~struck through~~ text.|
|`~~Mistake~~ corrected.`|`<del>Mistake</del> corrected.`|~~Mistake~~ corrected.|

You can also apply strikethrough to the middle of a word for emphasis:

|Markdown|HTML|Rendered Output|
|---|---|---|
|`This is striketh~~rough~~.`|`This is striketh<del>rough</del>.`|This is striketh~~rough~~.|
### Bold and Italic[](https://www.markdownguide.org/basic-syntax/#bold-and-italic)

To emphasize text with bold and italics at the same time, add three asterisks or underscores before and after a word or phrase. To bold and italicize the middle of a word for emphasis, add three asterisks without spaces around the letters.

| Markdown                                  | Rendered Output                         |
| ----------------------------------------- | --------------------------------------- |
| `This text is ***really important***.`    | This text is _**really important**_.    |
| `This text is ___really important___.`    | This text is _**really important**_.    |
| `This text is __*really important*__.`    | This text is _**really important**_.    |
| `This text is **_really important_**.`    | This text is _**really important**_.    |
| `This is really***very***important text.` | This is really_**very**_important text. |

 **Note:** The order of the `em` and `strong` tags might be reversed depending on the Markdown processor you're using.

---
## Lists[](https://www.markdownguide.org/basic-syntax/#lists-1)

You can organize items into ordered and unordered lists.

### Ordered Lists[](https://www.markdownguide.org/basic-syntax/#ordered-lists)

To create an ordered list, add line items with numbers followed by periods. The numbers don’t have to be in numerical order, but the list should start with the number one.

| **Markdown**                                                                                                        | **Rendered Output**                                                                                                  |
| ------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| `1. First item 2. Second item 3. Third item 4. Fourth item`                                                         | 1. First item  <br>2. Second item  <br>3. Third item  <br>4. Fourth item                                             |
| `1. First item 1. Second item 1. Third item 1. Fourth item`                                                         | 1. First item  <br>2. Second item  <br>3. Third item  <br>4. Fourth item                                             |
| `1. First item 8. Second item 3. Third item 5. Fourth item`                                                         | 1. First item  <br>2. Second item  <br>3. Third item  <br>4. Fourth item                                             |
| `1. First item 2. Second item 3. Third item`  <br>    `1. Indented item`  <br>    `2. Indented item 4. Fourth item` | 1. First item  <br>2. Second item  <br>3. Third item  <br>1. Indented item  <br>2. Indented item  <br>4. Fourth item |

# Horizontal Rules[](https://www.markdownguide.org/basic-syntax/#horizontal-rules)

A horizontal rule is used to create a visual break or divider in content. In Markdown, you can create a horizontal rule using three or more:

- Asterisks (`***`)
- Dashes (`---`)
- Underscores (`___`)

# Code in Markdown 

Markdown allows you to display code using **inline code** or **code blocks**, with optional syntax highlighting.  
## 1. Inline Code

Use backticks () to highlight small code snippets within a sentence. 
```
	Example: markdown Use the `git status` command to check your repository's status.
```

**Output:** Use the `git status` command to check your repository's status.

## 2. Code Blocks

For larger code sections, use triple backticks or tildes. Add the language name after the opening backticks for syntax highlighting.

```javascript
 function helloWorld() {   console.log("Hello, world!"); }
```

# Links[](https://www.markdownguide.org/basic-syntax/#links)

To create a link, enclose the link text in brackets (e.g., `[Duck Duck Go]`) and then follow it immediately with the URL in parentheses (e.g., `(https://duckduckgo.com)`).

```
My favorite search engine is [Duck Duck Go](https://duckduckgo.com).
```

The rendered output looks like this:

My favorite search engine is [Duck Duck Go](https://duckduckgo.com/).

# Linking Images[](https://www.markdownguide.org/basic-syntax/#linking-images)

To add a link to an image, enclose the Markdown for the image in brackets, and then add the link in parentheses.

```
	[![An old rock in the desert](/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)
```

The rendered output looks like this:

[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)

<center>This text is centered.</center>

# HTML Markdown

## Underline[](https://www.markdownguide.org/hacks/#underline)

Underlined text is not something you typically see in web writing, probably because underlined text is nearly synonymous with links. However, if you’re writing a paper or a report, you may need the ability to underline words and phrases. A couple of applications like [Bear](https://www.markdownguide.org/tools/bear/) and [Simplenote](https://www.markdownguide.org/tools/simplenote/) provide support for underlining text, but Markdown doesn’t natively support underlining. If your Markdown processor supports [HTML](https://www.markdownguide.org/basic-syntax/#html), you can use the `<ins>` HTML tag to underline text in your document.

```
Some of these words <ins>will be underlined</ins>.
```

The rendered output looks like this:

Some of these words <ins>will be underlined</ins>.

# Highlight 

> [!NOTE]  
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]  
> Crucial information necessary for users to succeed.

> [!WARNING]  
> Critical content demanding immediate user attention due to potential risks.
