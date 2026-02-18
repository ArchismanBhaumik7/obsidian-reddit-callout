# obsidian-reddit-callout
Simple CSS snippet that imitates a Reddit Post inside a callout in Obsidian.

## DISCLAIMER!
A non-insignificant portion of this code was written by / with help from Goolge's Gemini on Google AI Playground; however, most of the tweaks were made by me to make it just about right.
Do with this information what you will.

## Features:
- Imitates Reddit CSS, including Subreddit name, Time of Posting, Name of Poster and post flairs.
- Multiple choices for flair colors.
- Easily create your own color schemes for flairs.
- Option to give your callout posts Upvotes or Downvotes to emulate the feel of Reddit

## Usage
Download reddit.css and put it in the snippets folder inside your .obsidian config folder in your Vault.
After that, you need to open the Vault in Obsidian, open Settings > Appearance > Scroll down to "CSS Snippets" and turn on selector for reddit.css underneath it.
If it doesn't show up, try refreshing your snippets with the button beside "CSS Snippets", check what your config folder is set to, or restart Obsidian.

### Usage Format
In Obsidian, use the !reddit modifier inside the callout definition to activate this snippet.

It uses the consecutive paragraphs in your callout (the <p></p> tags) to identify and target the different components.

#### Important
I **highly recommend** that you copy the example callout from below and put it into your **Templates** folder as a file instead of trying to write it out entirely by yourself.
This is because, to make the look of the Callout title similar to Reddit, a lot of nested tags were used in the title, making it difficult to type it out correctly every time you want this callout. 
The easiest way would instead be to insert the callout as a template, then change the parts you want in it.

### Order of Content
1. The title line contains the following in order: 
    1. Name of Subreddit
    2. How long ago the post was made
    3. Name of Poster
2. The first paragraph of the body defines the flair for the post. **This is optional**.
3. 2nd Paragraph onwards is the body of the text. You can write as much as you want. **Make sure to an empty line** (an empty `>`) **between separate paragraphs**, otherwise the CSS won't get applied properly.
4. The last paragraph i.e. the last line of the callout represents the upvote count of the post.

#### Important
Since it applies CSS modifiers on paragraphs, you ***must*** put line breaks inside the callout to separate paragraphs.
A single newline is read as continuation of the same paragraph, so you need to add an extra newline after each section of the callout is complete.
On Desktop, this is achieved by pressing Shift+Enter.
On Mobile devices, there is usually a button to create a newline without breaking out of the callout. Alternatively, add a `>` in the new line and type there onwards.

### Modifiers
You can add modifiers with a `|` after defining the callout, as [!reddit | mod1 mod2].
1. For the callout icon, there are two in-built SVGs, taken directly from Reddit:
   - Use [!reddit | general] to get the r/ logo
   - Use [!reddit | 18] to get the 18 logo on reddit, used in NSFW subs without a sub icon
   - Without either of these the callout icon is gonna throw a blank
2. For flairs to show up, you need to use the `flair` modifier. The default flair is black text on orange background.
3. If you want to change the color of the flair, use `orange-f`, `blue-f`, `yellow-f` and `green-f` **alongside the flair modifier**. Currently these are the only 4 colours I have implemented, but you can define your own background and text colors by opening the CSS file and copying the format there. You can also use `nsfw-f` to show the default flair Reddit applies to 18+ posts.
4. `upvote` and `downvote` can optionally be used to change the vote pill.

### Examples
Code:
```
> [!reddit| general flair upvote] <div><p><span>r/Obsidian</span><span>•</span><span>3 hours ago</span></p><p><span>u/Creator</span></p></div>
> Meme
>
>Second Paragraph onwards, it's the main content of the Callout. 
>
>Make sure to separate paragraphs with a blank line so different paragraphs are properly recognized!
>
>1.2k

> [!reddit| 18 flair nsfw-f downvote] <div><p><span>r/ObsidianNSFW</span><span>•</span><span>3 hours ago</span></p><p><span>u/Creator</span></p></div>
> NSFW
>
>You can make as many paragraphs as you wish. Until the last paragraph, it will be rendered as the body text; the last paragraph is for the upvote count of the post.
>
>60
```
Output:
...

Code:
```
> [!reddit| general] <div><p><span>r/Obsidian</span><span>•</span><span>3 hours ago</span></p><p><span>u/Creator</span></p></div>
> 
> Hello, this is a post without a flair and an un-voted pill.
>
>Lorem ipsum and so on...
>
>2

> [!reddit| general flair green-f] <div><p><span>r/Obsidian</span><span>•</span><span>3 hours ago</span></p><p><span>u/Creator</span></p></div>
> Original Post!
>
>You can also use green, blue, orange, or yellow colored flairs!
>
>If that doesn't seem enough choice, you can define your own color schemes very easily!
>
>12
```
Output:
...

## Further Development
I made this snippet primarily for my own use, but decided to share it just in case someone would like something like this. As such, I am quite happy with how it has turned out to be and am probably not going to work on this too much. You are free to do what you want with this.

That being said, I think there are a few things I would eventually like to improve at some point:

### Visual
- Get feedback on and improve this snippet's aesthetics in Light Mode in other custom themes.
- Possibly add non-functional "Comments" and "Share" button for further immersion

### Functional
- Style nested callouts to imitate comments on Reddit