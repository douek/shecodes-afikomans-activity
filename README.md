# shecodes-afikomans-activity
 &#x202b; מבנה של אתר שאפשר להתחיל ממנו ולהוסיף לו

https://codepen.io/douek/pen/JjEXmQe

&#x202b; בתחתית המסך יש אפשרות לשכפל למשתמש שלך
 <img width="1792" alt="Screen Shot 2021-03-27 at 14 27 21" src="https://user-images.githubusercontent.com/12955333/112719213-d02c3300-8f08-11eb-8ee6-2a73e949e6a8.png">


## Text when hovering
טקסט שמופיע רק כש&#x202b; hover מעליו.
אפשר לבחור טקסט שכבר קיים או להוסיף חדש. לדוגמה כותרת (h1-h6) או פסקה (p).
יש להוסיף לתגית class דוגמה:

```html
<p class="find-me">Yay you found me!</p>
```

ולהוסיף את ה&#x202b;css הבא:
&#x202b; הצבע הראשון צריך להיות הצבע של הרקע
 &#x202b; הצבע השני יהיה הצבע של הטקסט כשעוברים מעליו עם הסמן
 
 ```css
 .find-me {
  color: #fff
}

.find-me:hover {
  color: #555
}
 ```
&#x202b; הצבעים תלויים בצבע הרקע - הדוגמה היא על טקסט ברקע הלבן. הצבעים הקיימים בטמפלייט (רקע) הם:

&#x202b; לבן
```css
color: #fff
```
&#x202b; אפור
```css
color: #f5f5f5
```
&#x202b; ירוק
```css
color: #229954
```

&#x202b; צבעי טקסט קיימים :

&#x202b; לבן (על רקע ירוק)
```css
color: #fff
```
&#x202b; אפור כהה (על שאר הרקעים)
```css
color: #555
```

&#x202b; אפשר לעשות טריק דומה על לינקים כפתורים ועוד

&#x202b; אפשר להכיל את החוק שכאשר עושים hover על משהו אחד הוא משפיע על משהו אחר לדוגמה

HTML
```html
<a href="#" class="btn hover-me">Hover Me</a>
<p class="find-me" >You found Me</>
```
CSS
```css
.find-me {
  visibility: hidden;
}

.hover-me:hover + .find-me {
  visibility: visible;
}
```

&#x202b; השתמשתי פה בproperty visibility אבל אפשר להשתמש גם בצבעים כמו בדוגמה למעלה


## Konami Code - javascript
&#x202b; תופיע התראה כאשר מקישים למעלה למעלה למטה למטה שמאל ימין שמאל ימין ש a b
&#x202b; יש לשים את הקוד המלא בsection של javascript  בקודפן
```javascript
var pattern = ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight', 'b', 'a'];
var current = 0;

var keyHandler = function (event) {

	// If the key isn't in the pattern, or isn't the current key in the pattern, reset
	if (pattern.indexOf(event.key) < 0 || event.key !== pattern[current]) {
		current = 0;
		return;
	}

	// Update how much of the pattern is complete
	current++;

	// If complete, alert and reset
	if (pattern.length === current) {
		current = 0;
		window.alert('You found it!');
	}

};

// Listen for keydown events
document.addEventListener('keydown', keyHandler, false);
```
&#x202b; הסבר מפורט על איך זה עובד נמצא כאן (אנגלית)

https://gomakethings.com/how-to-create-a-konami-code-easter-egg-with-vanilla-js/#:~:text=The%20Konami%20Code%20is%20Up,would%20give%20you%2030%20lives.

&#x202b; דוגמה של הקוד רץ

https://codepen.io/cferdinandi/pen/qBWVPqL

## Console Messgae
&#x202b; הודעות שיוצגו בconsole כאשר פותחים את הdevtools
&#x202b; יש לשים את הוקד הבא תחת הsection של javascript, אפשר לשנות את הטקסט
&#x202b; אפשר גם לשנות את הצבעים

```javascript
console.log('%c Enter Text Here ', 'background: #222; color: #bada55');
```

&#x202b; כדי לצפות בזה עובד צריך לפתוח את הdevtools של הדפדפן:
- F12
- Or press Command + Option + C (Mac) or Control + Shift + C (Windows, Linux, Chrome OS).

&#x202b; וללכת לטאב console

## Special Messgae For Specifc Input
&#x202b; הודעה מיוחד שתקפוץ כשמקלידים משהו ספיציפי בשדה email 
TODO

## &#x202b; רעיונות נוספים (אנגלית)
- https://www.willmaster.com/library/features/how-to-make-an-easter-egg.php
- https://dev.to/rose/playing-with-easter-eggs-ideas-for-making-your-website-more-fun-1p0p


## &#x202b; מקורות
- https://www.bryanbraun.com/2018/04/01/several-ways-to-hide-easter-eggs-on-your-website/
- https://codepen.io/javpet/pen/QqMWgd
