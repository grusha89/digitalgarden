---
title: Table of content
---


### Navigation

- [[Help]]
- [[User Account menu]]
- [[Navigation side panel]]
- [[Context menu]]
- [[Custom views]]
- [[Pagination]]


### Document detail

unique sections by document kind

- [[Document detail. Incoming Invoice]]
- [[Document detail. Outgoing Invoice]]
- [[Document detail. Receipts]]
- [[Document detail. Income cash receipts]]
- [[Document detail. Orders]]
- [[Document detail. Contracts]]
- [[Document detail. Others]]

shared sections

- [[Document detail. Tags]]
- [[Document detail. Approval]]
- [[Document detail. Accounting fields]]
- [[Document detail. Payments]]
- [[Document detail. Custom properties]]
- [[Document detail. Linked documents]]
- [[Document detail. Navigation]]
- [[Document detail. Comments]]
- [[Document detail. Event log]]
- [[Document detail. Validations]]
- [[Document detail. Actions]]
- [[Document detail. Lines]]
- [[Document detail. Files]]
- [[Manual forms]]
- [[Document detail. VS, KS, SS]]
- [[New document turning into Filled]]

### Documents grid

- [[Grid. Document upload]]
- [[Grid. Internal number import]]
- [[Grid. Exports]]
- [[Grid. Tags]]
- [[Grid. Filters]]
- [[Grid. Search]]
- [[Grid. Bulk actions]]
- [[Grid. Single actions]]
- [[Grid. Columns]]

### Employee expenses

- [[Accounts and cards]]
- [[Transaction]]
- [[Personal expenses]]
- [[Transaction filters]]
- [[Transaction and document pairing]]
- [[Accesses]]

### Bank

- [[Bank connections]]
- [[Account movements]]

### Settings 1

Marketplace (Prismatic)

- [[General settings]]

Registers administration

- [[Cost objects]]
- [[Number series]]
- [[Organization]]
- [[Contacts]]
- [[Accountant]]
- [[Items]]
- [[Payments]]

Notifications

- [[Notifications]]


### Settings 2

- [[My profile page]]
- [[Organization profile]]
- [[Security]]
- [[Users and permissions]]
- [[Approval paths]]
- [[Document types]]
- [[E-mails (Collecting)]]
- [[Customization. Custom properties]]
- [[Customization. Appearance]]
- [[Customization. Field settings for ERP]]
- [[Customization. Validations]]
- [[Customization. Print templates]]
- [[Integrations. API accesses]]
- [[Integrations. Extraction]]
- [[Integrations. ERP]]
- [[Integrations. Export]]
- [[Integrations. Bank]]
- [[Integrations. Signi]]
- [[Workflow automations]]


### Storage

- [[Storage. Navigation]]
- [[Storage. The grid]]
- [[Storage. The file detail]]


### Organization management

- [[Navigation]]

- [[Account settings]]
- [[Administrators]]
- [[Organizations]]
- [[API clients]]
- [[Rossum]]


### Onboarding

- [[New customer registration]]
- [[Quick organization setup]]
- [[Demo organization]]


### Other

- [[Automatic pairing order with incoming invoice]]
- [[Account wflow]]
- [[Access to the document]]
- [[ARES]]
- [[Dashboard]]
- [[Downloading]]
- [[Error notifications]]
- [[ISDOC]]
- [[Legislations]]
- [[Not VAT payer organizations]]
- [[Offline mode]]
- [[Recycle Bin]]
- [[Inputs]]
- [[Keyboard shortcuts]]
- [[Tables]]
- [[Tooltips]]

### Rossum integration

- [[Data movement from wflow to Rossum]]
- [[Extraction and flow statuses]]
- [[Fields from PDF that are being extracted]]
- [[Document split]]
- [[Rossum. Bank account validation]]
- [[Rossum. Custom properties]]
- [[Rossum. Dates]]
- [[Rossum. Lines]]
- [[Rossum. Recapitulation]]
- [[Rossum. Validations]]
- [[Automatic sorting to the organization]]



<!-- ### Link syntax

To link to another note, you can use multiple syntaxes. The following four use the "double-bracket" notation ([view the Markdown source file](https://github.com/maximevaillancourt/digital-garden-jekyll-template/blob/master/_notes/your-first-note.md#link-syntax) to see the underlying syntax).

- Using the note title: [[a note about cats]]
- Using the note's filename: [[cats]]
- Using the note's title, with a label: [[A note about cats|link to the note about cats using the note title]]
- Using the note's filename, with a label: [[cats|link to the note about cats using the note's filename]]

You can organize notes in subdirectories and link them normally. For example, the links above all point to the `_notes/animals/cats.md` file. Here's another example: [[tigers]].

Non-latin languages are supported: [[안녕하세요]]; so are accents/diacritics: [[bon appétit!]]

Dashes and underscores in file names are supported, and may be omitted in the bracket link syntax. As an example, the `your-first-note.md` file can be linked to with [[your first note]] or [[your-first-note]], or even [[yOuR-FiRsT Note]].

In all cases, if the double-bracket link does not point to a valid note, the double brackets will still be shown, like this: [[there is no note that matches this link]].

Alternatively, you can use regular [Markdown syntax](https://www.markdownguide.org/getting-started/) for links, with a relative link to the other note, like this: [this is a Markdown link to the note about cats](/cats){: .internal-link}. Don't forget to use the `.internal-link` class to make sure the link is styled as an internal link (without the little arrow).

Since the Web is all about HTML, you can always use plain HTML if you want, like this: <a class="internal-link" href="/cats">This is a link to the note about cats with HTML</a>.

Of course, you can also link to external websites, like this: [this is a link to Wikipedia](https://wikipedia.org/). Again, you can use plain HTML if you prefer. Footnotes are also supported and will be treated like internal links.[^1] You can point to other notes in your footnotes.[^2]

[^1]: This is a footnote. For more information about using footnotes, check out the [Markdown Guide](https://www.markdownguide.org/extended-syntax/#footnotes).
[^2]: This is another footnote that links to the note about [[cats]]. You may also point to [[notes that do not exist]] if you wish.

### Tweet embedding

Note: This behavior is disabled by default for privacy reasons. See "Site configuration" section below to enable it.

You may include a tweet URL on its own line (like below), and it would be replaced with an official Twitter embed if the site configuration demands it.

https://twitter.com/jack/status/20

### Media embedding

You may embed media files within a note using HTML5 media tags. Here's an example for an audio file:

"Jazzy Frenchy" by Benjamin Tissot from bensound.com
<audio controls>
  <source src="{{ site.baseurl }}/assets/jazzyfrenchy.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

### Site configuration

Some behavior is configurable by tweaking the `_config.yml` file.

**`use_html_extension`**: if you use a static host that doesn't support URLs that don't end with `.html` (such as Neocities), try changing the `use_html_extension` value to `true` in the `_config.yml` file and restart the Jekyll server (or re-build the site). This adds a `.html` extension to note URLs and may resolve issues with links. If you're still having trouble, I recommend using Netlify to host your digital garden: it's free, easy to use, and fully supports this template's features out of the box.

**`open_external_links_in_new_tab`**: when set to `true`, this makes external links open in new tabs. Set to `false` to open all links in the current tab.

**`embed_tweets`**: when set to `true`, tweet URLs on their own lines will be replaced with a Twitter embed. Default value is `false`.

### Automatic bi-directional links

Notice in the "Notes mentioning this note" section that there is another note linking to this note. This is a bi-directional link, and those are automatically created when you create links to other notes.

### Link previews

If you're on a device with mouse support, try hovering your mouse on internal links to preview the notes: [[a note about cats]].

Links that have been previewed will be cached to avoid redundant requests.

### Images and other Markdown goodies

Finally, because you have the full power of Markdown in this template, you can use regular Markdown syntax for various formatting options.

Lists work as expected:

- List element A
- List element B
- List element C

1. List element
2. List element
3. List element

If you'd like to quote other people, consider using quote blocks:

> Lorem ipsum dolor sit amet

And of course, images look great:

<img src="{{ site.baseurl }}/assets/image.jpg"/>

You can also ==highlight some content== by wrapping it with `==`.

Non-latin languages are supported too: ==你好==, ==안녕하세요==, ==こんにちは==.

### Code syntax highlighting

You can add code blocks with full syntax color highlighting by wrapping code snippet in triple backticks and specifying the type of the code (`js`, `rb`, `sh`, etc.):

```js
// Here's a bit of JavaScript:
if (a === b || c == d)
  console.log('hello!')
```

```rb
# And now some Ruby
def foo(bar)
  "baz"
end
```

```sh
$ cat /dev/urandom | grep "the answer to life" # shell scripts look nice too
```


### Next steps

This digital garden template is free, open-source, and [available on GitHub here](https://github.com/maximevaillancourt/digital-garden-jekyll-template).

The easiest way to build your own digital garden based on this template is to read this [step-by-step guide explaining how to set this up from scratch](https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll).

Go forth, have fun, and learn new something every day! ✌️ -->
