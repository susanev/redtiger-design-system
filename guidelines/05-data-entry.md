---
layout: page
title: Data entry
group: guidelines
permalink: /guidelines/data-entry.html
description: High-level form guidelines

---

## General guidelines
* Only present information that the user is able to change as a form element (e.g., asset ID should not be displayed in a form element because it is not possible for the user to change it)
* All buttons should use the semantic button element
* Representing navigation in a select menu should be avoided
* Tool-tips must become visible on keyboard focus, hover, and click and should only be used when its not possible to provide extra information in the label itself
* Placeholder text is never suitable as a label

### Labels
* In almost all cases form elements must have labels 
* Labels and form elements create a one-to-one relationship (i.e., a single label should not describe multiple form elements, and multiple labels should not describe a single form element)
* Form elements must be associated with their labels
* If needing to use a form element without a label (e.g., Search) then an aria-label must also be provided
* If using an asterisk to indicate required, that asterisk must be in span tags with aria-hidden set to true

### Check boxes and radio buttons
* Check boxes and radio buttons should only be used when more than 1 option can be selected
* Check boxes and radio groups should be grouped when the label does not give enough information
* Use check boxes instead of multi-select menus which are not accessible
* If a radio button is required, it should start with a selection

## References
* [Webaim accessible form techniques](https://webaim.org/techniques/forms/)
* [Mozilla accessible HTML](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)