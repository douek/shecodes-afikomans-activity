# shecodes-afikomans-activity
 &#x202b; מבנה של אתר שאפשר להתחיל ממנו ולהוסיף לו

https://codepen.io/douek/pen/BappLyj?editors=0010

&#x202b; בתחתית המסך יש אפשרות לשכפל למשתמש שלך
 <img width="1792" alt="Screen Shot 2021-03-27 at 14 27 21" src="https://user-images.githubusercontent.com/12955333/112719213-d02c3300-8f08-11eb-8ee6-2a73e949e6a8.png">

## Konami Code - javascript
&#x202b; תופיע התראה כאשר מקישים למעלה למעלה למטה למטה שמאל ימין שמאל ימין a b
&#x202b; ככה נראה הקוד המלא - כולו צריך להכתב בsection של הjavascript בקודפן.
```javascript
// הגדרה של משתנים
// התבנית של הקוד שאנחנו רוצות
const pattern = [
  "ArrowUp",
  "ArrowUp",
  "ArrowDown",
  "ArrowDown",
  "ArrowLeft",
  "ArrowRight",
  "ArrowLeft",
  "ArrowRight",
  "b",
  "a"
];
// משתנה שיעזור לנו לעקוב אחרי התקדמות בהקלדת הקוד
let current = 0;

// הפונקציה שתרוץ ברגע שמקש ילחץ
const keyHandler = function (event) {
  // בדיקה האם המקש שנלחץ הוא המקש הבא בתבנית
  if (pattern.indexOf(event.key) < 0 || event.key === pattern[current]) {
    // טיפול במקש נכון
    current++;
  } else {
    // טיפול עם המקש שנלחץ הוא המקש הלא נכון
    current = 0;
  }

  // בדיקה האם כל התבנית הסתיימה
  if (pattern.length === current) {
    // הצגת הודעה ואיפוס
    current = 0;
    window.alert("You found it!");
  }
};

// הקשבה לאירוע לחיצת כפתור והגדרת הפונקציה שתרוץ ברגע שזה יקרה
document.addEventListener("keydown", keyHandler, false);

```

# &#x202b; צעדים לכתיבת הקוד

## &#x202b; הגדרת משתנים

&#x202b; המשתנה הראשון הוא בעצם התבנית וזה המקשים שיקושו שיגרמו להתראה
&#x202b; כאן בדוגמה זה קונאמי הקלאסי אבל הן יכולות לתת איזו תבנית של אותיות שהן רוצות - **באנגלית**

```javascript
const pattern = ["ArrowUp", "ArrowUp","ArrowDown","ArrowDown","ArrowLeft","ArrowRight","ArrowLeft","ArrowRight","b", "a"];
```

&#x202b; המשתנה השני הוא מספר מעקב שעוזר לנו לעקוב באיזה שלב בתבנית אנחנו נמצאות (בתו הראשון, בתו השני וכו׳)

```javascript
let current = 0;
```

## &#x202b; השלב הבא הוא השלמת הפונקציה שתרוץ בכל פעם שנלחץ מקש - המסגרת כבר תיהיה מוגדרת

&#x202b; הפונקציה מקבלת פרמטר בשם event
&#x202b; הפרמטר בעצם מכיל פרטים על האירוע שקרה - במקרה הזה לחיצת כפתור ובעזרתו נדע איזה כפתור נלחץ


&#x202b; אנחנו נבדוק האם המקש שנלחץ הוא שווה למקש בתבנית
&#x202b; ובמידה והוא נכון נקדם את המספר מעקב שלנו בפלוס אחד כדי שבמקש הבא נבדוק אותו מול המקש הבא בתבנית


&#x202b; במידה והמקש הוא לא נכון נחזיר את המעקב ל0


&#x202b; הצלחה היא כאשר מספר התווים הנכונים שהוקלדו שווים ערך לגודל התבנית
&#x202b; במידה והצלחנו נציג התראה למשתמש 
&#x202b; ונאפס את המעקב כדי לאפשר התחלה מחדש של התבנית 



&#x202b; והדבר האחרון שנשאר לעשות הוא לרשום את הפונקציה לאירוע של לחיצת מקש
&#x202b; אפשר להסביר פה מזה זה אירועים

```javascript
// הפונקציה שתרוץ ברגע שמקש ילחץ
const keyHandler = function (event) {
  // בדיקה האם המקש שנלחץ הוא המקש הבא בתבנית
  if (event.key === pattern[current]) {
    // טיפול במקש נכון
    current++;
  } else {
    // טיפול עם המקש שנלחץ הוא המקש הלא נכון
    current = 0;
  }

  // בדיקה האם כל התבנית הסתיימה
  if (pattern.length === current) {
    // הצגת הודעה ואיפוס
    current = 0;
    window.alert("You found it!");
  }
};

```

# &#x202b; תקלות נפוצות
- חסרה נקודה פסיק או סוגריים איפשהו
- הן מקלידות את הקוד בזמן שהן בשפה עברית ולא אנגלית (רלוונטי אם משתמשות באותיות)

# &#x202b; מקורות
&#x202b; הסבר מפורט על איך זה עובד נמצא כאן (אנגלית)

https://gomakethings.com/how-to-create-a-konami-code-easter-egg-with-vanilla-js/#:~:text=The%20Konami%20Code%20is%20Up,would%20give%20you%2030%20lives.

&#x202b; דוגמה של הקוד רץ

https://codepen.io/cferdinandi/pen/qBWVPqL
