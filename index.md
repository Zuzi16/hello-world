
### A fun interactive tutorial aimed for keen users of the R programming language, to kick back and enjoy some cool and interesting simple functions of R.

Everyone, from professional statisticians working in big corporations analyzing data, to undergraduate students, can get stuck while trying something in R. Besides, the mind is a muscle and like every muscle it gets tired after hours and hours of working. This tutorial introduces the fun side of R, aiming to provide a useful break for you if, nothing makes sense anymore, and you are just looking at letters and numbers at 3 am in the morning.

## beepr

Let’s start with a boisterous one. Our first R function is beepr. Install and load this package:

```{r}
#install.packages(“beepr”)
library(beepr)

```

You can also install the development version of beepr through github:

```{r}
# install_github(“rasmusab/beepr)
```

What does beepr do, you ask?
Try writing: beep() in your script and run the code.


```{r}
beep()
```

Your toasted bread is ready!
This is the default sound of beepr; a “ping” sound. You can hear the same sound by writing beep(1)
Now try 

```{r}
beep(2)
```

Yes, that is the sound when mario gets the coin. Cool isn’t it?

There are 11 possible sounds, feel free to try them all now, I ll wait.

Not that you asked, but my favourites are beep(8) (mario sound) and beep(10) (facebook sound). Can’t beat the classics am I right?

Keep in mind that you can also write the names of the sounds in the place of the numbers.

e.g., beep(“ready”) for beep(6).

Here is the list for all the sounds with their appropriate numbers and names:

1.	"ping"
2.	"coin"
3.	"fanfare"
4.	"complete"
5.	"treasure"
6.	"ready"
7.	"shotgun"
8.	"mario"
9.	"wilhelm"
10.	"facebook"
11.	"sword"

The whole function can also be written in this way:

beep(sound = “number/name of sound”, expr= NULL)

e.g.

```{r}
beep(sound= 5, expr= NULL)
```

So, is there any real use in this function? Sure there is. You can incorporate it in other functions, so that you can hear the beeping function that you choose when the particular part of the code has been run by R. This can be extremely useful when you are running programs that take a lot of time to be completed. That way you don’t need to check your computer every minute to see when you can continue, on coding.  Beepr has got that covered for you.

beepr package provides another function: the “beep_on_error” function. Tough to guess what this does, so let me help you. It beeps when you have an error in your code. Not as useful as the beep function but we still like it.

beep_on_error() uses the same numbers and names for sounds as the beep() function. Lets try an example:

```{r}
beep_on_error(sound = 10, expr= NULL)

```

Try writing something that does not make sense now

In the first line there was no problem so…silence

In the second line the function recognized an error so…you got a friend request!

As famous swede R programmer Error Errorson has said:
“Better an error that speaks, than one that remains silent”


### fortunes 

Speaking of famous quotes, let’s check out our next function, that’s called “fortunes”. Probably the most well-known just-for-fun package in R, fortunes has been providing consolation to dejected statisticians all around the globe. Go on, install it and load it!

```{r}
#install.packages(“fortunes”)
library(fortunes)

```

And let’s try it

```{r}
fortune()
```
What did you got?
Wise words for sure. Try that again! 

You see that every time you run the code, another quote comes up in your console.
These are short nuggets of wisdom and humour, that are taken by R-help forums. The humour is very nerdy so its understandable if you cringe. If you re a fellow coding nerd, you re welcome!

Fortune() picks a random quote. However, you can be more selective.

Lets try

```{r}
fortune("Ripley")
```

That brings up a quote from Ripley. Brian Ripley might not be “The talented Mr Ripley”, but he has talents on spatial statistics and pattern recognition (He is one of the primary R developers). Having retired from the Oxford university he is still one of the most active committers in R. Every time we write “Ripley” on the fortune function, we can see one of the insights Ripley has shared with us. But enough with my random encyclopaedic information. Let’s learn from the greats!

Putting names of developers and committers in R provides you with their quotes. There are over 400 quotes in there so, don’t worry its not going to get repetitive. And if you happen to not know any other R developers, its ok!

You can write a number:
```{r}
fortune(4)
```

Picks the quote assigned for number 4. 
You can always try fortune() that picks a random one, too.

And what if you have a specific problem in mind. Fortune can provide a random thought on this matter.

Last week I had to do some coding for my Data Science course. I was stuck, not knowing how to use the parse() function. 

Smart as I am I wrote the following piece of code.

```{r}
fortune("parse", showMatches = TRUE)
```

PICTURE

This was one of the 5 available pieces of wisdom for parse(). I soon realized that I in fact didn’t need to use the parse() function. 

FUN FACT: Some quotes can be found answering other ones. 

```{r}
fortune("parse.*answer", fixed = FALSE)
```

Thanks for the input, Greg!

And if you’re ready to be showered with wisdom use the lapply() (to apply a function over a numeric vector) and the setNames() function, to be able to choose more than one quote.

Try this:

lapply(setNames(, c(38, 106, 129)), fortune)


Can’t get any better than that, can it?

## cowsay

The question here is what is better than random wisdom quotes popping out of nowhere.

The answer is animals saying the quotes. Ladies and Gentlemen, I hereby present to you the best function of them all; “cowsay”.

But let’s not get ahead of ourselves. One step at a time.

```{r}
#install.packages(“cowsay”)
library(cowsay)

```
“cowsay”, much alike “fortunes” uses only one function. In this case it’s the say() function

Ok lets run it!

Try say() which is default for say(“Hello world!”)


```{r}
say()
```
You expected a cow, didn’t you? I will make up I promise.

```{r}
say("Moo may represent an idea, but only the cow knows.\n --Mason Cooley",
   by = "cow")


```

You can write whatever quote you’d like, however there are about 30 different animals (and more!) to choose from. You can just try writing one, and if it the specific animal doesn’t exist, an error message will let you know of the options you have. Allow me to go with yoda any time of the day.

And speaking of time of the day these little creatures can also tell you the time.


```{r}
say("time")
```
I think its time for a random cat fact

```{r}
say("catfact")
```
Unfortunately say() does not provide random ASCII pictures (that’s what they re called), so in order to achieve that we need to make our own function.

Other functions needed to achieve this, are sample(), names(), and paste()


```{r}
anybody_ihopeitsyoda_say_hello <- function() {
  animal <- sample(names(animals), 1)
  say(paste("Hello, I'm a ", animal, ".", collapse = ""), by = animal)
}
anybody_ihopeitsyoda_say_hello()

```

If you use Windows, you may get an error message the first time. This is because some “animals” cannot be used this way. If you don’t use Windows, you got lucky, as these animals excluded are super cool. If you do, Yoda is included so its fine you can ignore that.

What did you get? Did my wish come true?

Imagine that it took 17 people to develop this masterpiece. This is truly humanity working together for the better good.

### Fun fact: If this seems familiar at all, it’s because this is one of the oldest fun-functions ever. It was first developed in Unix, one of the first computer operating systems developed in the late 60s. “cowsay” originally had a cow speaking as default, thus the name. Cool move by R developers incorporating it in their packages.

### Another fun fact: Did you notice the letters on our creatures? These are the signatures of the developer of each ASCII. Some are unsigned (“nosig”). Have a go TRYING to find them!

Don’t mind me just adding some more cool things you can do with "cowsay".

```{r}
say("Q: What do you call a solitary shark\nA: A lone shark", by="shark")

```

By using multicolor() and crayon()

```{r}
#install.packages(“multicolor”)
#install.packages(“crayon”)
library(multicolor)
library(crayon)

say("boo!", "ghost", 
    what_color = "cyan", by_color = "saddlebrown")

```

You make not only the animal colourful, but also his opinion.

There’s only the option of adding more than one colours to your creation.

```{r}
say(what = "I'm a rare Irish buffalo",
    by = "buffalo", 
    what_color = c("salmon2", "darkcyan", "salmon2", "darkcyan"),
    by_color = c("green", "white", "orange"))

```
Again as with "beepr", "cowsay" can be used to soften the blow of "error" or "warning" messages. 

```{r}
say(what = "Warn you I!", by = "yoda", type = "warning")
```
Kept you waiting, but here you go:

```{r}
say("fortune")
```
There you go! A cat providing us of its insight on a specific matter on R .

You want more? Again with the use of the same functions, like paste(), sample() and names() we can have a random animal providing us a random opinion.


```{r}
someone_pls_be_yoda_say_my_fortune <- function() {
  animal <- animal <- sample(names(animals), 1)
  say(paste(fortune(), collapse = "\n"), by = animal)
}
someone_pls_be_yoda_say_my_fortune()

```

Go nuts!

Cant believe I almost forgot! We all love horses, but what about endless ones? 

{r}
endless_horse()

Allow me to say that this function is R’s kryptonite. R can do incredibly complicated models, but always surrenders to the mercy of “endless_horse”.

R continues to run this function creating a taller and taller horse, that might be our civilizations last reminder in the future 

You can interrupt R by pressing the "Stop" sign in the top right corner of the script.


### CalendR

Short break with a more down-to earth function.
```{r}
#install.packages(“calendR”)
library(calendR)

```

"CalendR" function can prove incredibly useful. Just running the function, shows the yearly calendar for 2021

```{r}
calendR()
```
If we want to see the calendar for 2022

```{r}
calendR("2022")
```
Let's see about January.

```{r}
calendR(year= 2022, month= 1)
```
Let’s try make it more pretty.

```{r}
calendR(year= 2022, month= 1,
        start = "M",
        special.days = "weekend",
        special.col  = "cyan"
        )

```

Ok this is starting to look useful. You can work marvels with “calendR” (it can actually replace other calendars, thanks to its versatility)

But we are not here for that. We’re here to get silly. Let’s see what day my grandma was born.

```{r}
calendR(year= 1941, month= 12,
        start = "M",
        special.days = "weekend",
        special.col  = "cyan"
)

```
Thursday 25 of December

What about Jesus Christ (Don’t try this at history class, due to major historic inaccuracies)

Write this:

calendR(year= -1, month= 12,
        start = "M",
        special.days = "weekend",
        special.col  = "cyan"
)

Well, sorry R for having an inquiring mind!

```{r}
calendR(year= 1, month= 1,
        start = "M",
        special.days = "weekend",
        special.col  = "cyan"
)

```
We can live with that...

### Fun

So far so good right? Do you have fun? If you do, imagine how much you are going to enjoy a package named “Fun”. Can’t be bad, can it?

Go ahead install and load it.


```{r}
#install.packages(“fun”)
library(fun)

```
Functions inside this package, allow you to play games. You read right, games. 

For games to be operable, we first have to open the right interactive graphics device on our computer system.


```{r}
if (.Platform$OS.type == "windows") {
  x11()
} else {
  x11(type = "Xlib") }

```
x11 being our interactive graphics device. "if. else" function is used

Did you see a small window popping? This is where you can play the majority of the games. Have fun!

```{r}
mine_sweeper()  
lights_out()
gomoku()
sliding_puzzle()

```

Make sure to go easy on playing more than one games during a session, R can get overloaded and crash! Don’t forget to open your interactive device each time.

```{r}
tower_of_hanoi()
alzheimer_test()


```
For more info about these games press these links:

Tired of playing games? Just shut them all down with:

```{r}
#shutdown()
```

Welcome back! Can’t believe you fell for that. Don’t worry I fell for that too the first time. For those cunning enough to not listen to everything I’m saying (i’m just a random guy on the internet after all) or people that have come by this function again, or even knowledgeable programmers for that matter, shutdown() shuts down all operations on your computer (i.e. shuts down your computer)

Can’t think of a random password for your top-classified Deliveroo account? Just run: 
```{r}
random_password()
```
### Praise

Unfortunately, are approaching the end of this tutorial. All good things have to end. You’ve done pretty good. No. As a matter of fact you’ve done great! I’m sure you did.

You deserve not only my praise but Rs praise as well. You’ve read right!
Try this:

```{r}
#install.packages(“praise”)
library(praise)

praise("${Exclamation}! Kind reader, you're ${adjective}!")
```
I don’t know about you but according to R I am primo!
If that’s not convincing enough for you, try capital letters in “Exclamation”

```{r}
praise("${EXCLAMATION}! Kind reader, you're ${adjective}!")
```

Well, someone is fishing for compliments now! 

People come and go, even pets do…praise() will be always there for you, either if you've  completed a task on R or elsewhere, or you just need some love. 

And there’s more!
```{r}
praise("${EXCLAMATION}! You have done this ${adverb_manner}!")
```
Here’s a whole list of entries on this function:

1.adjective
2.adverb
3.Adverbs.
4.adverb_manner
5.Adverbs of manner, with positive meanings.
6.created
7.Synonyms of ‘create’ in paste tense.
8.creating
9.Synonyms of ‘create’, in present participle form.
10.exclamation
11.Positive exclamations.
12.rpackage
13.Synonyms for the term ‘R package’.


Most of us are immersed in coding, some of you are doing serious projects in R, and loads of the times we may get frustrated with R. These functions are here to remind us of what attracted us into coding for the first time. The fun of it!

So, every time you get hopeless trying to do Bayesian Statistics, go back to these functions. Or even incorporate some of them in your code. From personal experience it helps. And worst case scenario, save your work first(!!!), then run shutdown() and go hang with your friends. Coding can wait!

Here is where I would thank you for giving your time to go through this tutorial but I’m going let R do that for me.
```{r}
praise("Thanks for reading, I hope you had some fun ${creating} your own ${adjective} functions!")
```

