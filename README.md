# Update
The author of the original repo has split the repos into an embedding one and a wildcard-only one, so the original reason for creating this fork is gone:
https://github.com/Klokinator/Umi-AI-Wildcards

# Fork
The weird commit numbers stem from the fact that I purged the git history to not download 1gb worth of embeddings every time.

The wildcards in the derrian directory come from https://gitgud.io/psuedo/wildcards_stuff, it includes some very nice recursive ones.

Most of the wildcards in user directory come from wonderful users of Touhou Project AI discord, thanks guys.

I advise using this with https://github.com/DominikDoom/a1111-sd-webui-tagcomplete.

## Installation 
Install it as you would any other extension, either by:
 - dropping the URL `https://github.com/Tsukreya/Umi-AI-debloat.git` into the install from URL box and pressing install.
 - or running `git clone https://github.com/Tsukreya/Umi-AI-debloat` inside the webui extensions folder.
   
Either way a restart of the webui if you have it currently running is advised, so that the autocomplete extension (which I recommend once again) to pick up on the wildcards.

### Settings override usage:
Values that you can override are: `cfg_scale, sampler, steps, width, height, denoising_strength`
You would do so by wrapping those in `@@` and assigning a value. You can specify multiple overrides in one `@@` block using `,` as a separator:
`@@width=512, height=768@@`
`@@width={512|768}, height={512|768}@@`

Using `,` as a separator is a change from the original repo which used `|` as a separator, but I found it ambiguous and too messy when setting wildcard values for setting overrides directly in the prompt.

### Below is the usage taken directly from UmiAI's wiki:

* `{a|b|c|...}` will pick one of `a`, `b`, `c`, ...
* `{x-y$$a|b|c|...}` will pick between `x` and `y` of `a`, `b`, `c`, ...
* `{x$$a|b|c|...}` will pick `x` of `a`, `b`, `c`, ...
* `{x-$$a|b|c|...}` will pick atleast `x` of `a`, `b`, `c`, ...
* `{-y$$a|b|c|...}` will pick upto `y` of `a`, `b`, `c`, ...
* `{x%a|...}` will pick `a` with `x`% chance otherwise one of the rest

* `__text__` will pick a random line from the file `text`.txt in the wildcard folder

* `<[tag]>` will pick a random item from yaml files in wildcard folder with given `tag`
* `<[tag1][tag2]>` will pick a random item from yaml files in wildcard folder with both `tag1` **and** `tag2`
* `<[tag1|tag2]>` will pick a random item from yaml files in wildcard folder with `tag1` **or** `tag2`
* `<[--tag]>` will pick a random item from yaml files in wildcard folder that does not have the given `tag`
* `<file:[tag]>` will pick a random item from yaml file `file`.yaml in wildcard folder with given tag

WebUI Prompt Reference

* `(text)` emphasizes text by a factor of 1.1
* `[text]` deemphasizes text by a factor of 0.9
* `(text:x)` (de)emphasizes text by a factor of x
* `\(` or `\)` for literal parenthesis in prompt
* `[from:to:when]` changes prompt from `from` to `to` after `when` steps if `when` > 1 or after the fraction of `current step/total steps` is bigger than `when`
* `[a|b|c|...]` cycles the prompt between the given options each step
* `text1 AND text2` creates a prompt that is a mix of the prompts `text1` and `text2` can be modified by adding `:x` like `text1:x AND text2:y`

<details><summary>Original README file.</summary>
    
# Umi AI: A WebUI Wildcard Mod!

Umi AI is a wildcard mod that allows you to create randomized characters from random species with modular clothing types. It will grow over time and eventually become the ultimate character randomizer and creator.

Umi replaces the [Dynamic Wildcards extension](https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards). It has all the same functionality, plus more. Umi also conflicts with the [Unprompted extension](https://github.com/ThereforeGames/unprompted). Pick one or the other.

Note that if you are reading this message a substantial amount of time after the date of Nov 13th, Umi may already have the majority of capabilities that Unprompted does. Additionally, it will almost certainly be easier to use. For example, what if you want to create a random choice of multiple options?

**Unprompted formatting**:

    Photo of a [choose]red|blue|yellow|green[/choose]-haired [choose]man|woman[/choose]

**Umi formatting**:

    Photo of a {red|blue|yellow|green}-haired {man|woman}

These two functions do exactly the same thing, but Umi's is smaller and easier to read. The goal of Umi is to be as easy to use as possible while providing consistently high-quality outputs of random characters and settings.

# Installing Umi

Installing Umi is easier than ever. It has been simplified into a 3-step process.

**Step 1: Determine if your PC meets the requirements to run AI generation.**
Is your GPU sufficiently powerful enough to run AI generation? [Download and run Speccy](https://www.ccleaner.com/speccy) and [post your PC specs in the Umi AI Discord](https://discord.gg/9K7j7DTfG2).

Assuming your PC meets the requirements...

**Step 2: Run the WebUI auto-installer.**
Download the latest version of Automatic1111's WebUI Autoinstaller from here. It will be the .exe file.
https://github.com/EmpireMediaScience/A1111-Web-UI-Installer/releases

![enter image description here](https://i.imgur.com/0u8KwOt.png)

Follow the Autoinstaller's steps to get WebUI up and running. There will be some parts that need to download large multi-GB files, so be patient. If you run into issues, [join the Umi AI Discord to ask for help](https://discord.gg/9K7j7DTfG2).

**Step 3: Install the Umi AI Extension.**
Once WebUI is open and running, navigate to the Extensions tab at the top, and the Install from URL sub-tab.

![enter image description here](https://i.imgur.com/gBqmnyz.png)

Paste the Umi AI URL in, like shown above.
https://github.com/Klokinator/UnivAICharGen.git

Press Install, and you'll be ready to start randomly generating with Umi AI!

At this point, you can just [join the Umi AI Discord](https://discord.gg/9K7j7DTfG2) to learn all the nuances of how to use Umi AI properly as well as share your characters!
</details>
