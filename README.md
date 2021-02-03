# I-Ching-Interpretations
The .plist libraries from which I-Ching, App of Changes generates readings. 

I publish a Cordova app on Google Play and the Apple Store called "I-Ching: App of Changes" that's based on a digital version of the book I created in Turbo Pascal back in the 1980s. Yes. I'm that old. 

My original app contained the Wilhelm-Baynes translations of the oracle, modified for gender neutrality and modernizing much of the languate, with my own interpretations. Over the years, I've had interest from several people in providing alternative translations and interpretations in the app. 

The purposee of this repo is to privide the XML structure that I use in .plist files in the app for anyone keen on porting other interpretations into the app. 

If you'd like to create an alternate library, drop me a line before you set out porting anything into this format. I am really happy to accommodate app users who want their own version of the readings, but need to consider copyright issues, quality of text, and probably a dozen other things before bundling them into the app. I cannot promise that I will include your library! I'm a hobbyist developer, this app barely makes enough money to cover costs, and I have many other calls on my time from running a small creative agency to doing my best to combat climate change to spending time with my family. 

But all that said, I would love to be able to offer a wider selection than just the original Chinese and my own interpretations. 

The structure of each file is a dictionary of dictionaries. The book is a dictionary, and each Hexagram is a dictionary, thus:

```html
<dict>
	<key>乾 (qián), The Creative </key>
	<dict>
		<key> Judgement </key>
		<array>
			<string>The Creative works sublime success,</string>
      (... any number of translation strings ...)
      <string>*<string>
      (... any number of interpretation strings ...)   
    <key>Image</key>
		<array>
      <string></string>
     </array>  
    <key>Line1</key>
		<array>
      <string></string>
    <array>
      (... Line2, Line3, Line4, Line5 ...)
    <key>Line6</key> 
		<array>
      <string></string>
    <array>
  </dict>
      
  <key>坤 (kūn), The Receptive </key>
      (...61 more hexagrams)
      
  </key>
 </dict>      
      
      
```
Note that asterisk! It's treated programatically as the break point between a translation and an interpretation. It gets rendered as a tiny image of the hexagram. In cases where you only provide translation it's optional. But to maintain a consistent aesthetic and ensure users know what's original and what's not, make sure it sits between the two if you're doing both. See the Wilhelm-Baynes-Fitzgerald version here to see it in action.  

A few things to be aware of: 

The text is UTF-8. So oddly Chinese characters work fine, but you need to render some special characters as HTML tokens for them to work, e.g apostrophes need to look like this: "\&apos;" When in doubt, just make sure it all parses as valid XML and all should be well. 





