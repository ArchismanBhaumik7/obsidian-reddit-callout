# obsidian-reddit-callout
Simple CSS snippet that imitates a Reddit Post inside a callout in Obsidian.

## DISCLAIMER!
A significant portion of this code was written by / with help from Goolge's Gemini on Google AI Playground; however, most of the tweaks were made by me to make it just about right.
Do with this information what you will.

## Installation
Download reddit.css and put it in the snippets folder inside your .obsidian config folder in your Vault.
After that, you need to open the Vault in Obsidian, open Settings > Appearance > Scroll down to "CSS Snippets" and turn on selector for reddit.css underneath it.
If it doesn't show up, try refreshing your snippers with the button beside "CSS Snippets", and check what your config folder is set to.

## Usage Format
In Obsidian, use the !reddit modifier inside the callout definition to activate this snippet.

It uses the consecutive paragraphs in your callout (the <p></p> tags) to identify and target the different components.

### Order of Content
1. The write the "name of the subreddit" just beside the callout name, as >[!reddit] r/ObsidianMD
2. The first paragraph of the callout body is the time of posting, i.e. how long ago the post was made
3. The second paragraph refers to the poster
4. The third paragraph defines the flair for the post. **This is optional**.
5. 4th Paragraph onwards is the body of the text. You can write as much as you want.
6. The last paragraph i.e. the last line of the callout represents the upvote count of the post.

#### Important
Since it applies CSS modifiers on paragraphs, you ***must*** put line breaks inside the callout to separate paragraphs.
A single newline is read a being the same paragraph, so you need to add an extra newline after each section of the callout is complete.
On Desktop, this is achieved by pressing Shift+Enter.
On Mobile devices, there is usually a button to create a newline without breaking out of the callout.

### Modifiers
You can add modifiers with a `|` after defining the callout, as [!reddit | mod1 mod2].
1. For the callout icon, there are two in-built SVGs, taken directly from Reddit:
   - Use [!reddit | general] to get the r/ logo
   - Use [!reddit | 18] to get the 18 logo on reddit, used in NSFW subs without a sub icon
   - Without either of these the callout icon is gonna throw a blank
2. For flairs to show up, you need to use the `flair` modifier. The default flair is black text on orange background.
3. If you want to change the color of the flair, use `red-f`, `blue-f`, `yellow-f` and `green-f` **alongside the flair modifier**. Currently these are the only 4 colours I have implemented, but you can define your own background and text colors by opening the CSS file and copying the format there.

### Example
To add...

## Further Development
I made this snippet primarily for my own use, but decided to share it just in case someone would like something like this. As such, I am quite happy with how it has turned out to be and am probably not going to work on this too much. You are free to do what you want with this.

That being said, I think there are a few things I would eventually like to improve at some point:

### Visual
- Put subreddit name and time of post on a single line with the poster name just beneat it, and the callout icon next to this entire block, similar to how reddit displays this information.
- Get feedback on and improve this snippet's aesthetics in Light Mode in other custom themes.

### Functional
- Add modifiers that can fill the upvote and downvote arrow keys to make it appear that you have liked/disliked the post.
