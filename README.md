<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cascading Effect in CSS</title>

<style>
    /* 1. Low specificity: element selector */
    p {
        color: blue;
        font-size: 18px;
    }

    /* 2. Higher specificity: class selector */
    .highlight {
        color: green;
    }

    /* 3. Even higher specificity: ID selector */
    #special-text {
        color: orange;
    }

    /* 4. !important overrides all */
    .force-red {
        color: red !important;
    }

    /* 5. Same specificity as first rule, but later in source order */
    p {
        font-size: 22px; /* This will override the earlier font-size */
    }
</style>
</head>
<body>

<h1>CSS Cascading Effect Demo</h1>

<p>This paragraph is styled only by the element selector (blue text).</p>

<p class="highlight">This paragraph is styled by both element and class selectors (green text wins).</p>

<p id="special-text" class="highlight">
This paragraph is targeted by element, class, and ID selectors (orange text wins due to higher specificity).
</p>

<p id="special-text" class="highlight force-red">
This paragraph has all the above rules, but <strong>red wins</strong> because of <code>!important</code>.
</p>

</body>
</html>
