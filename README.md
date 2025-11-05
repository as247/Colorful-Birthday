# 🎨 The Colorful Birthday Standard — v1.0

**Colorful Birthday** defines a symbolic and systematic way to assign a *color identity* to every birthday and to discover *colorful connections* between dates across the year.

It transforms the traditional idea of a birth date into a colorful, cyclic system of time — linking months, numbers, and meaning.

---

## 🧭 Overview

Every person’s birthday belongs to one of four **primary color groups**, inspired by the **CMYK color model**, representing four emotional and seasonal stages of the year.

| Month Range | Assigned Color | Birthday Type | Meaning |
|--------------|----------------|----------------|----------|
| January – March | **Cyan** | *Cyan Birthday* | Freshness, clarity, beginnings |
| April – June | **Magenta** | *Magenta Birthday* | Emotion, creativity, expression |
| July – September | **Yellow** | *Yellow Birthday* | Energy, warmth, growth |
| October – December | **Black** | *Black Birthday* | Depth, reflection, completion |

Each birth month defines the **base color** of a person’s *Colorful Birthday Identity*.

---

## 🧩 Colorful Birthday Matching Logic

In addition to the main birthday color, each person also has a set of **Colorful Birthdays** — symbolic dates throughout the year that “resonate” with their original date of birth.

### Definition

> A date is considered a **Colorful Birthday** if its month and day numbers together contain both digits of the person’s birth date (month and day), regardless of order.  
>  
> If multiple dates in the same month meet this condition, only the **first matching day** of that month is recognized as the Colorful Birthday.

### Concept

In other words, a Colorful Birthday reflects a **numerical resonance** between the original birth date and other dates in the calendar.  
The digits of one’s birth month and day reappear — sometimes in reversed order — across the months of the year, forming a sequence of symbolic **color echoes**.  
Only the earliest occurrence per month is kept to ensure simplicity and uniqueness.

---

## 🧮 Reference Implementation (PHP)

```php
function getColor($month){
    switch ($month) {
        case 1:case 2:case 3: return "Cyan Birthday";
        case 4:case 5:case 6: return "Magenta Birthday";
        case 7:case 8:case 9: return "Yellow Birthday";
        case 10:case 11:case 12: return "Black Birthday";
        default: return "Invalid Birthday";
    }
}

function getColorfulBirthdays($month, $day){
    $birthdays = [];
    for($i=1; $i<=12; $i++){
        for($j=1; $j<=getDaysInMonth($i); $j++){
            if(
                (str_contains((string)$month, (string)$i) && str_contains((string)$day, (string)$j))
                ||
                (str_contains((string)$month, (string)$j) && str_contains((string)$day, (string)$i))
            ){
                $birthdays["$i-$j"] = getColor($month);
                break; // First matching day per month
            }
        }
    }
    return $birthdays;
}
function getDaysInMonth($month) {
    // Return number of days in given month
}
```

## 📘 License

The **Colorful Birthday Standard** is published under a dual license model:

- **MIT License** for all source code files.  
- **Creative Commons Attribution 4.0 International (CC BY 4.0)** for all documentation and written materials.

You are free to use, remix, and share both — with proper attribution to  
**© 2025 — The Colorful Birthday Project**.
