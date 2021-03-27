# shecodes-afikomans-activity

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
&#x202b; הצבעים תלויות בצבע הרקע - הדגומה היא על טקסט ברקע הלבן. הצבעים הקיימים (רקע) הם:

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
&#x202b; הסבר מפורט על איך זה עובד נמצא כאן
https://gomakethings.com/how-to-create-a-konami-code-easter-egg-with-vanilla-js/#:~:text=The%20Konami%20Code%20is%20Up,would%20give%20you%2030%20lives.
