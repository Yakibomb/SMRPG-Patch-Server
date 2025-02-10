GOAL: This is a small collection of hacks each intended for use as a base for a complete project. I wanted to create something that anyone could use to jumpstart progress for their SMRPG hacking project or, perhaps, to inspire one. My intention was to alter the game in one aspect as much as possible so as to create a solid backdrop to work from, and to do so without interfering with any other steps in the process.

PURPOSE: To relieve others from hours of gruntwork. By doing this, I thought I could provide both incentive for and a headstart on creating any such hack where the main character is someone other than Mario! I'm sure everyone likes that idea.

WARNING: This hack has been sitting for months unfinished but untouched, so I finally decided to just put it out here. Unfinished animations are limited to just these:
1. Toadstool's swimming
2. Mallow's swimming
3. Mallow's sleeping(?)
4. Mallow's star-get pose (deemed unnecessary through event scripts)
5. Geno's sleeping
6. All characters' small upward swimming (a la Midas River)

(Watch the videos below!)
(These are demonstration vids only. The weapons/magic used were hacked in just to show you that it looks awesome.)

Toadstool: http://www.youtube.com/watch?v=ezyoXHIsw-4
Mallow: http://www.youtube.com/watch?v=rrhUf4blWWM
Geno: http://www.youtube.com/watch?v=ErszX6T1wAY

PROS AND CONS:
There are good things to anticipate, as well as the bad things you should worry about.

PROS:
- Each respective character can do what Mario can do, and more.
Because Peach/Mallow/Geno uses much less space than Mario does, I was able to fit in plenty of animations for each.
- No redundancies and pixel-perfection.
I took care to ensure that there were no repeated tiles in Mario's BPP graphics, that most unused spaces were indicated (by greyed-out tiles), and that all animations intended to mimic original Peach/Mallow/Geno animations were exact.
- There is even some free space.
By the aforementioned reasons, there is also room to create some custom sprites/animations if the hacker sees fit.
- Characters can still rely on their original animation scripts.
As in, their animations for weapons and spells. Equipping Mario with another character's weapon, for example, will produce a seamless attack sequence.
- Small Mario and 8-bit Mario have been replaced accordingly!
For the sake of completion, I took all the liberties necessary. (See Toadstool's video for her transformation.)
- Can be applied at any time.
Since graphics were the only element I changed, the .ips can be used to fill in over the graphics at any stage in the hacking process. (See instructions at bottom.)

CONS:
- There is a lack of uniformity and, sometimes, coherent organization.
Each character needed a different approach as to how they can fit over Mario's sprite, so I improvised at many stages in the editing. (Some tiles are isolated from related tiles, and so on. Only an issue if you plan to make custom sprites)
- Original spritework is minimal.
Due to my own lack of skill, I was not able to animate a complete, natural set of movements for the characters. They look awkward while moving directly N, S, E, or W because I (mostly) referred to existing tiles for these animations.
- As-is, there are graphical glitches.
If you choose not to make a hack from scratch, a lot of workarounds will be needed to cover up certain glitches (for example, during the first star-get scene). I'm fairly sure these are memory issues.
- Not all animations made it.
To avoid issues with memory, I chose not to try and include all the characters' unique animations. I was able to cover Mario's major animations (tumbling, balancing, etc.) but some animations wouldn't fit, so I had to scrimp on ones such as Mallow's long-arm-running animation used during the Forest Maze running scene. In addition, all Riding Yoshi sprites were scrapped.
I removed them in favor of fitting each character's broad range of emotions into the {006} moldset.
- The (walking, up-right) animations for Toadstool/Mallow/Geno are unusable for their original sprite.
For the sake of accuracy and to avoid complications in memory, I decided that Mario should use the (walking, up-right) animations from each respective character, and edit theirs instead of his own. Because Mario's BPP GFX are organized differently, these animations will be unusable by their original counterparts. This means that having an identical character in your party will be impossible (including pallette edits of the character) unless they trade with Mario's (walking, up-right) animation set and have it edited as well.

General notes:
- Yes, Bowser isn't included in the package. I would have loved to have him (in fact, he's who I started with), but due to the cumbersome size of his sprite, Bowser will need a very different approach compared to the other three and is a project all its own.
- Applying only these hacks will obviously not produce anything presentable. Actual dialogue and such is a no-brainer (not to mention having character duplicates in your party), but as a bare example, event scripts will have to be edited to display different molds (e.g. when entering pipes).
- If any spriters would like to complete this work with proper animations, please contact me when you do so. I can consolidate your work into this post with the proper updates and credits.


No credit necessary if used!


Instructions:
1. Apply the .ips to a clean unheadered ROM.
2. Open the desired ROM with Lazy Shell (e.g. your hack).
3. Use Lazy Shell's option to "Import elements from another ROM" (top toolbar).
4. Browse to the patched ROM from step 1. Then, from the list, check only "Sprites".
5. Click OK and save. 
