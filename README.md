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


## 
