# PiRogue
An implementation of Rogue in Picat

## Why?

I have an interested in creating games with procedurally generated narrative, and have a fondness for the roguelike genere. 
Picat has a number of features that make it idea for both of these. By re-creating Rogue I hope to:
* Get a feel for programming in Picat on a larger scale project.
* Create a roguelike with clear boundaries to avoid feature creep on my first pass.

## Process

I'm following [How to write a roguelike in 15 steps](http://roguebasin.roguelikedevelopment.org/index.php?title=How_to_Write_a_Roguelike_in_15_Steps)
to give my project a bit of structure, here's how I'm doing.

### Step 1 - Decide to write a game:: DONE

Deciding to make a clone of course made this easy. To prepare for the programming end and come up with a very broad idea of how
to implement I've reviewed the [Picat Docs](http://picat.orgfree.com/picat_guide/picat_guide.html). There's a lot to it, I
suspect it won't be my last pass through.

### Step 2 - Hello world!: DONE 

Parts of this were straightforward, tools:
* Language: Picat, clearly
* Editor: Emacs
* OS: Cygwin in windows
* Source Control: Git

While doing this I wanted to test that the two main interactions worked:
* Clear a screen & print to it
* Read in just one character

This was a bit more complicated than I'd planned on. You can find my solutions to both of these problems (made with the help
of the kind folks at the [Picat Forum](https://groups.google.com/forum/#!forum/picat-lang).

### Step 3 - It's a boy!: DONE | Tag: Step3

#### 2019-08-15

It's starting to at least look like rogue. I'm creating a set of structures that represent the world state and 
I'm using the constraint system to display the screen. I still need to move the character around, but that should
be pretty easy, I think I'll try to have it behave correctly with walls too.

#### 2019-08-16

I've found that debugging this code can be a serious nightmare because circumstances that would
cause an exception in other languages simply evaluate to `no.` So I've put together a seriously
adhoc unittest system. For now it only works on equality on function returns, but since I'm
already expanding out my predicates, including predicates that are using constraints, I'm going
to have to expand it.

On the plus side, I have a game loop, the character still doesn't move, but you can run the game
with `picat rogue.pi` and exit the loop with `q`.

#### 2019-08-19

We have motion! The `@` can now be moved around using the standard rogue keys:

```
Y K U
 \|/
H- -L
 /|\
B J N
```

And walls will block movement. The code for the walls was surprisingly much harder to figure out
how to write, and much simpler once completed than I'd expected, and it should extend fairly well
as I expand out to having doors & hallways.

The other challenge that I discovered during this process was that there was a noticeable (> 0.1 sec)
flicker each time the screen refreshed. It would seem that clearing the screen is moderatley
expensive.  To mitigate this instead of clearing the screen each move I'm moving the cursor to
the top of the screen using an ASCII command sequence. I have no idea how well this will port
across systems, but it seems to work well enough in Cygwin.

Alright, bagging and tagging this one. On to generating maps.

### Step 4 - The map: TODO
### Step 5 - Saving/Loading: TODO
### Step 6 - It's alive! Alive!: TODO
### Step 7 - Interaction: TODO
### Step 8 - Data files: TODO
### Step 9 - Items: TODO
### Step 10 - Magic: TODO
### Step 11 - Simple game: TODO
### Step 12 - Levels: TODO
### Step 13 - Experience: TODO
### Step 14 - Citizens: TODO
### Step 15 - Free at last: TODO
