# لوحة المفاتيح المتوازنة – Mutawazin keyboard layout

## A comfortable, speedy and efficient Arabic keyboard layout

Inspired by the design principles of OJ Bucao’s English *Workman keyboard layout* I redesigned the Arabic keyboard layout with comfort, speed and efficiency in mind.

![Mutawazin Keyboard Layout](https://raw.githubusercontent.com/orchid6/Mutawazin-Arabic-keyboard/master/Images/Mutawazin%20Arabic%20Keyboard.png) 

Here’s the quick summary, full details and discussion follows the install instructions.

### Advantages: 
* __63% key load on the eight home keys;__ means more comfort, speed and efficiency. PC (33%) and Apple (34%).
* __80% load on the easiest keys;__  means more comfort, speed and efficiency. PC (41%) and Apple (45%). 
* __Only 4% load on the hardest to press keys__; means less finger and wrist strain. PC (37%) and Apple (37%). 
* __The layout respects the natural motion of the fingers__; less lateral movement of the fingers and wrists means more comfort, speed and efficiency.
* The compact design significantly reduces finger travel; __save 3880 meters in finger moment (43%) and 7 hrs 10 mins__ of typing time if typing out the Quran compared to PC and Apple. (See below for more details.)
* __7% same finger bigram load and 43% same hand bigram load;__ means more alternation between the fingers and the hands for faster typing. PC (10%/46%) and Apple (15%/45%).
* __50%/50% load balance between left and right hand__. PC (39%/61%) and Apple (42%/58%).
* __Familiar location for punctuation keys__.
* __All eight diacritics (Tashkil) marks on *two* fingers__ for super ease access whether you add them as you go or afterwards.

#### Disadvantages:
* Learn a new layout – but remember you only need to __learn once but move your fingers and wrists each time__. It'll feel so good to learn something new that will benefit you significantly.

# Installation


## Windows
Step 1) Download the Windows intallation files [here](https://github.com/orchid6/Mutawazin-Arabic-keyboard/releases/download/v1/Windows.zip)

Step 2) Run the `setup.exe`

Step 3) Open `Settings` -> Click on `Time & Language`-> Click on `Language`-> Under the "Preferred languages" section, select the Arabic or default language -> Click the `Options` button -> Under the "Keyboards" section, click the `Add a keyboard` button -> Select Mutawazin keyboard layout -> Well done!

Step 3) Alternatively check out this Microsoft [guide to adding layouts](https://support.microsoft.com/en-us/help/258824/how-to-change-your-keyboard-layout).

Step 4) `Windows key` + `Spacebar` keyboard shortcut to quickly change between the available keyboard layouts.

## Mac
Coming soon. (Any help with this would be appreciated.)

## Linux

Step 1) Open the Arabic XKB symbols file:
`sudo gedit /usr/share/X11/xkb/symbols/ara`

Step 2) Copy and paste the contents of Mutawazin's XKB symbols file [here](https://github.com/orchid6/Mutawazin-Arabic-keyboard/blob/master/Mutawazin%20Linux%20XKB) to the bottom of the Arabic XKB file. Save and exit.

Step 3) Open `evdev.xml` to add Mutawazin as a layout option:
`sudo gedit /usr/share/X11/xkb/rules/evdev.xml`

Step 4) Add the layout declaration after the `<variantList>` tag. Save and exit. __Tip__: Once you've opened `evdev.xml` use `Ctrl+F` to find `<name>ara</name>` this will get you to the right place.

Layout declaration:

```    
<variant>
          <configItem>
            <name>mutawazin</name>
            <description>Arabic (Mutawazin)</description>
          </configItem>
        </variant>
	       <variant>
          <configItem>
            <name>mutawazin_digits</name>
            <description>Arabic (Mutawazin/digits)</description>
          </configItem>
        </variant>
```

`evdev.xml` before:
```
      <configItem>
        <name>ara</name>
        
        <shortDescription>ar</shortDescription>
        <description>Arabic</description>
        <countryList>
          <iso3166Id>AE</iso3166Id>
          ...
        </countryList>
        <languageList>
          <iso639Id>ara</iso639Id>
        </languageList>
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>azerty</name>
            <description>Arabic (azerty)</description>
          </configItem>
        </variant>
        <variant>
```
`evdev.xml` after:
```
      <configItem>
        <name>ara</name>
        
        <shortDescription>ar</shortDescription>
        <description>Arabic</description>
        <countryList>
          <iso3166Id>AE</iso3166Id>
          ...
        </countryList>
        <languageList>
          <iso639Id>ara</iso639Id>
        </languageList>
      </configItem>
      <variantList>
        <variant>
          <configItem>
            <name>mutawazin</name>
            <description>Arabic (Mutawazin)</description>
          </configItem>
        </variant>
	       <variant>
          <configItem>
            <name>mutawazin_digits</name>
            <description>Arabic (Mutawazin/digits)</description>
          </configItem>
        </variant>
        <variant>
          <configItem>
            <name>azerty</name>
            <description>Arabic (azerty)</description>
          </configItem>
        </variant>
        <variant>
```

Step 5) Reload xkb-data: `sudo dpkg-reconfigure xkb-data`

Step 6) Add Mutawazin as the input source in the settings.

<img src="https://raw.githubusercontent.com/orchid6/Mutawazin-Arabic-keyboard/master/Images/Add%20an%20input%20source.png" alt="Add Mutawazin as the input source" width="600"/>

Step 7) `Windows/Super key` + `Spacebar` keyboard shortcut to quickly change between the available keyboard layouts.

# Full details and analysis:

## The design philosophy

### The keyboard zones:

_OJ Bucao_ correctly observed in his design of the (_English) Workman keyboard layout_ that some fingers like the index and middle finger are much stronger than say the pinky finger. Therefore more load should be placed on these fingers. Furthermore it is easier for longer fingers like the middle and ring fingers to stretch and easier for shorter fingers like the index and pinky fingers to fold.

Moreover _vertical_ movement is natural to the fingers, whereas _horizontal_ and _diagonal_ stretching is uncomfortable. So the most occurring letters need to be on keys that are the easiest to press; this will increase comfort, efficiency (finger travel) and therefore speed. Based on these observations the keyboard can be divided into 5 zones of comfort.

![Keyboard comfort zones](https://raw.githubusercontent.com/orchid6/Mutawazin-Arabic-keyboard/master/Images/Keyboard%20zones%20of%20comfort.png)
<img src="https://raw.githubusercontent.com/orchid6/Mutawazin-Arabic-keyboard/master/Images/Keyboard%20zones%20of%20comfort%20legend.png" alt="Legend" width="200"/>

1) The keys in the Core Zone are the easiest to press. The zone mainly consists of the home keys plus stretching for the middle and ring fingers and folding for the index finger.

2) The Inner Zone is a level slightly harder than the previous one: This zone includes two keys for each index finger that requires only a slight diagonal fold for the bottom key and a slight vertical stretch for the top key.

3) The Outer Zone is slightly less uncomfortable then the previous zone. Here the long middle and ring fingers need to fold which is harder for them then stretching and the short pinky finger does both stretching and folding. (Although it is easier for the short pinky finger to fold these bottom keys are included in this zone because the pinky is overall the weakest finger on the hand and so the load on it needs to be minimised.)

4) The Middle Column, this is a challenging place even for the strong index finger to reach because a high degree of uncomfortable horizontal and vertical stretching is required. Hence the use of these keys need to be minimised as much as possible.

5) Finally the End Zone includes the rest of the keys. It&#39;s the most challenging zone on the keyboard because firstly the weak pinky needs to be used and secondly it is required to significantly stretch horizontally and vertically. This should be a place of last resort as the whole wrist and hand may need to be moved to reach these keys. Therefore this zone is most suitable for rarely used but still necessary punctuation marks.

### Other considerations

- **Same finger Utilisation** : the same principle applies for fingers; it is faster to alternate between fingers even if on the same hand then to type key pairs with the same finger whilst other fingers are idle. Therefore Same Finger Utilisation should be low.
- **Same Hand Utilisation** : It&#39;s faster to use different hands to type a key pair (bigram like لا) than it&#39;s for the fingers to reach because it allows for the finger on the other hand to move into position before the press is required. Therefore Same Hand Utilisation should be low.
- **Load balance:** There should be balance between the load of keystrokes for each hand and for each type of finger. This will distribute the work to both hands, reduce strenuous load on one hand or one type of finger and therefore lead to more comfort, longer continuous typing sessions and so better speed.
- **Shift Key:** The use of the «Shift Key» should be minimised because it a) slows down typing and b) adds load to the pinky fingers.

## Letter frequency data:

Letter and letter pair (bigram) frequencies were calculated from the Arabic Leipzig Corpora Collection (Leipzig University). This source consists mainly of Arabic news websites.

**Words** : 210,563,004

**Arabic letters and ligatures** : 1,038,382,302

**Bigrams** : 821,555,724

**Sentences** : 9.9 million.

|| **Letter** | **Count** | **Percent** |
| --- | --- | --- | --- |
| 1 | ا | 162,092,509 | 15.61% |
| 2 | ل | 120,020,126 | 11.56% |
| 3 | ي | 80,348,056 | 7.74% |
| 4 | م | 65,041,978 | 6.26% |
| 5 | و | 56,336,237 | 5.43% |
| 6 | ن | 54,614,976 | 5.26% |
| 7 | ر | 48,712,444 | 4.69% |
| 8 | ت | 47,634,551 | 4.59% |
| 9 | ب | 35,425,341 | 3.41% |
| 10 | ع | 34,058,401 | 3.28% |
| 11 | ة | 33,005,989 | 3.18% |
| 12 | د | 31,360,729 | 3.02% |
| 13 | ف | 26,646,185 | 2.57% |
| 14 | س | 25,896,142 | 2.49% |
| 15 | ه | 25,322,511 | 2.44% |
| 16 | ق | 23,077,659 | 2.22% |
| 17 | ك | 20,086,770 | 1.93% |
| 18 | ح | 18,870,539 | 1.82% |
| 19 | أ | 18,199,623 | 1.75% |
| 20 | ج | 14,372,356 | 1.38% |
| 21 | ش | 9,912,424 | 0.95% |
| 22 | ط | 9,691,876 | 0.93% |
| 23 | ص | 9,630,608 | 0.93% |
| 24 | ى | 9,200,659 | 0.89% |
| 25 | خ | 8,544,594 | 0.82% |
| 26 | إ | 7,384,982 | 0.71% |
| 27 | ض | 6,939,174 | 0.67% |
| 28 | ذ | 6,691,257 | 0.64% |
| 29 | ز | 6,511,089 | 0.63% |
| 30 | ث | 5,621,929 | 0.54% |
| 31 | ئ | 4,628,974 | 0.45% |
| 32 | غ | 4,112,863 | 0.40% |
| 33 | ء | 3,616,524 | 0.35% |
| 34 | ظ | 2,306,589 | 0.22% |
| 35 | ؤ | 1,409,861 | 0.14% |
| 36 | آ | 1,055,777 | 0.10% |

There are 28 letters in the Arabic alphabet but some letters like ء (hamza) take up to 5 different forms (ligatures) depending on their position in the word. More on this later.

Based on the letter frequencies and the keyboard zones; the most frequent letters like ا and ل need to be placed on the home keys and rarely used letters like ظ (zah) and غ(ghain) can not justify their own key.

Some ligatures of ء like أ (_Alef with Hamza Above_) occur 503% more often than the pure form. In fact _Alef with Hamza Above_ is 19th on the table that&#39;s higher than 17 other letters and ligatures! These ligatures should be given their own key because they are very frequent.

The letter ء including all of it&#39;s ligatures has a combined frequency of 3.36%. That&#39;s position 10 in the table above. Putting all these letter forms in one key would increase the use of the «Shift Key» as well as the use of the «Alt-Gr Key» and «Alt-Gr Key» + «Shift Key» combo and it would still leave one form left. Use of the «Shift Key» needs to be minimised for both comfort and speed.

Some letters can be combined and need to be, in order to prevent a sprawl of letter into the end and middle column zones. It&#39;s effective to do so because their frequencies are very low and it will be easy to remember them because they are the same shape as their more frequently occurring sister. For example, ط (Tah) can be combined with ظ (zah).

Based on these frequencies and the design principles outlined above Mutawazin was designed.

Let&#39;s do some statistical analysis and compare Mutawazin to the Apple&#39;s Arabic keyboard and IBM/PC&#39;s Arabic keyboard the standard keyboards on laptops and desktops worldwide.

## Analaysis

### The home keys and keyboard zones

Firstly, on the eight home keys, the natural resting place of the fingers, Mutawazin boasts a 61% load compared to 33% for Apple and 34% for PC. That&#39;s equivalent to pressing 63 in every 100 keys without moving a finger. This is more efficient, comfortable and so faster.

Second, the core zone includes the home keys and the next six easiest to type keys. The more time fingers spend here the more comfortable and efficient they will be. On Mutawazin the core zone has a load of 81 out of every 100 keystrokes compared to only 41 PC and 45 on Apple. This means you will type 198% more in this comfortable zone compared to PC and 172% more compared to Apple. That&#39;s a lot of finger and wrist movement saved!

Third, in the challenging middle column that requires horizontal and diagonal stretching, Mutawazin has a load of only 4 out of every 100 keystrokes. On PC and Apple it&#39;s 33 out of every 100 keystrokes. That&#39;s a lot of uncomfortable index fingers&#39; stretching reduced.

Finally, on Mutawazin there are no letter keystrokes in the most difficult zone, the end zone. On PC it&#39;s 6 in every 100 keystrokes and on Apple 5 in 100 keystrokes.

Mutawazin has been designed to reduce load and therefore the difficulty of typing as you move your fingers out of the core. This is what makes typing more comfortable and enjoyable.

### Finger and hand loads

For maximum efficiency in typing the weight should be distributed between each type of finger whilst taking into account the relative strength of each finger. Give too much work to the index finger misses out on work that could be done on other fingers, especially the middle finger. There needs to be better weight distribution.

See how the fingers compare in Mutawazin: 35% (index) → 34% (middle) → 18% (ring)→ 14% (pinky).

PC: 55% (index) → 22% (middle) → 12% (ring)→ 12% (pinky).

Apple: 62% (index) → 18% (middle) → 11% (ring)→ 10% (pinky).

Looking at the weight profiles for each finger it&#39;s clear that the index fingers in both PC and Apple do more work (55% and 62% respectively) compared to Mutawazin&#39;s 35%. This may seem a good thing however reaching for the difficult middle column is not easy for the index finger. It involves difficult horizontal and diagonal stretching as mentioned already.

The weakest fingers are the pinkies, so the load on them needs to be minimised. Mutawazin&#39;s total pinky load is 14%, PC is 12% and Apple is 10%. Although both Apple&#39;s and PC&#39;s is lower then Mutawazin, it&#39;s important to note that 11% of the load in Mutawazin is on the pinky home keys. Whereas in both PC and Apple it&#39;s only 3% on the pinky home keys. So only 3% of the load for the pinky is in harder to reach positions in Mutawazin, whereas in PC and Apple it&#39;s 9% and 7% respectively.

The balance between each hand is 51%/49% on Mutawazin! Compare this with Apple&#39;s left hand load of 42% and right hand load of 58% and PC&#39;s left hand load of 39% and right hand load of 61%.

### Letters via «Shift Key».

On Apple 4.4% of load are letters accessed via the «Shift Key». On PC it&#39;s 2.6% and on Mutawazin it&#39;s 3.5%. Mutawazin has a lower shift load then Apple for the same number of keys with letters (27 keys). The shift key load is 1% less on PC but given it&#39;s full keyboard letter spread (34 keys) in effect it would be easier to press the shift key then to reach for some letters with the pinky on the edges of the keyboard.

### Finger travel and time saving:

The finger travel is the distance a finger moved from the centre of its home key to press the centre of the required key and then return home. If the next key is the same key as the previous key or if the key need is a home key no additional distance is added.

To write the Quran (72,010 words) would require a distance of 9063 (meters) on Apple, 9090m on PC and only 5183m on Mutawazin! **That&#39;s a 43% finger travel saving. What does that mean time wise?**

#### Time

To measure the distance a finger needs to travel is easy however working out the time taken is very difficult. This is because firstly, for example, some fingers like the middle finger travel the same distance faster than the pinky finger. Second, it&#39;s expected that stronger fingers will press keys faster than weak fingers. Finally, each person has a different speed due to practise, hand and finger sizes and wrist position and possibly other factors. But, for the sake of comparison, I will assume (based loosely on this paper [here](https://www.researchgate.net/publication/237105161_The_Great_Keyboard_Debate_QWERTY_versus_Dvorak)) that it takes the &#39;average&#39; typist 0.25s to press a home key and a finger (regardless of type) will travel at a max speed of 8cm/s to press all other keys; this speed includes the time need to press the key, which would be miniscule compared to the time needed to travel to it.

So how long would it take to type the Quran? On Apple that&#39;s 2403 minutes, on PC it&#39;s 2398 mins and on Mutawazin 1970 mins: **that&#39;s 7 hours 13 mins saved compared to Apple and 7 hrs 8 mins compared to PC.**

Hence the same &#39;average&#39; person would achieve a relative speed of 36.5 wpm on Mutawain and 30 wpm on Apple and PC. **That&#39;s a 22% increase in speed!**

(Note: although PC&#39;s distance is greater it takes less time to type compared to Apple due to three &#39;لا&#39; ligatures accessible via shift key. These ligatures are not accessible on Apple and are formed automatically by typingل and ا. On PC this saves a very small amount of time as fewer keys need to be pressed compared to Apple.)

### Bigrams

The top 20 bigrams are listed below. There are a total of 1296 theoretical bigrams in Arabic (36^2). 1292 were actually detected in the corpus, this makes sense as the rules of Arabic grammar prevent pairs like ا and ا appearing together for example.

|| **Bigram** | **Percent** |
| --- | --- | --- |
| 1 | (&#39;ا&#39;, &#39;ل&#39;) | 8.25% |
| 2 | (&#39;ل&#39;, &#39;م&#39;) | 1.63% |
| 3 | (&#39;ل&#39;, &#39;ا&#39;) | 1.43% |
| 4 | (&#39;ي&#39;, &#39;ة&#39;) | 1.25% |
| 5 | (&#39;ف&#39;, &#39;ي&#39;) | 1.25% |
| 6 | (&#39;ا&#39;, &#39;ن&#39;) | 1.22% |
| 7 | (&#39;و&#39;, &#39;ا&#39;) | 1.17% |
| 8 | (&#39;م&#39;, &#39;ن&#39;) | 1.11% |
| 9 | (&#39;ا&#39;, &#39;ت&#39;) | 1.06% |
| 10 | (&#39;م&#39;, &#39;ا&#39;) | 1.01% |
| 11 | (&#39;ر&#39;, &#39;ا&#39;) | 0.91% |
| 12 | (&#39;ا&#39;, &#39;ر&#39;) | 0.90% |
| 13 | (&#39;ي&#39;, &#39;ن&#39;) | 0.86% |
| 14 | (&#39;ل&#39;, &#39;ي&#39;) | 0.85% |
| 15 | (&#39;ل&#39;, &#39;ت&#39;) | 0.80% |
| 16 | (&#39;ر&#39;, &#39;ي&#39;) | 0.76% |
| 17 | (&#39;ي&#39;, &#39;ا&#39;) | 0.74% |
| 18 | (&#39;ع&#39;, &#39;ل&#39;) | 0.74% |
| 19 | (&#39;ل&#39;, &#39;ى&#39;) | 0.73% |
| 20 | (&#39;ه&#39;, &#39;ا&#39;) | 0.73% |

Firstly typing two letters using the same finger is slower then alternating fingers, this is also the case with the hands; it&#39;s faster to type with alternating between hands.

Of all the bigrams only 7% of the load will be typed by the same finger, compared to 10% for PC and 15% for Apple. This means there will be more alterations between the fingers which will increase efficiency and comfort because other fingers can move into position before they are needed.

The same principles applies to hands; the more alteration that occurs, the more comfortable and efficient the typing will be. On Mutawazin 43% of the load will be typed by the same hand compared to 46% on PC and 45% on Apple.

What about bigrams what require the use of the shift key? 10 in every 1000 bigrams will be typed by the same finger and will require a «Shift Key» press either before or after. In PC it&#39;s 3 in every 1000 and in Apple 13 in every 1000. Again, although PC has fewer letters under the shift key it is more difficult to reach them. In order to reach certain letters like ذ, د , ج and ط, the pinky needs to move a significant distance. It would be easier to just press the «Shift Key» instead of shifting the entire hand to reach these letters.

Finally bigrams on the same hand involving the shift key: on Mutawazin the load is 2.78% and 2% on both PC and Apple. In this particular instance higher is better because it is easier to alternate hands less if using the shift key.

### Conclusion


In conclusion, Mutawazin&#39;s better performance in load management, finger and hand balance, fewer same finger and same hand bigrams make it a superior choice in keyboard layout. It&#39;s true that there will be a learning curve but the benefits for your hands, wrists and fingers and typing experience overall in the long term clearly present a monumental benefit.

Check out all the data in the spreadsheet [here](https://github.com/orchid6/Mutawazin-Arabic-keyboard/blob/master/Full%20Stats.xlsx?raw=true).

# Dedication

To all writers, who, through their words, shed light on darkness. May this layout benefit you. Ameen.

# References
- Goldhahn, T. Eckart &amp; U. Quasthoff: Building Large Monolingual Dictionaries at the [Leipzig Corpora Collection](https://wortschatz.uni-leipzig.de/en/download/): From 100 to 200 Languages.
 In: _Proceedings of the 8th International Language Resources and Evaluation (LREC&#39;12), 2012_
- Hempstalk (2006). [The Great Keyboard Debate: QWERTY versus Dvorak](https://www.researchgate.net/publication/237105161_The_Great_Keyboard_Debate_QWERTY_versus_Dvorak).
