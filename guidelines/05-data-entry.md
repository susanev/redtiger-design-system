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
* Always group related fields together

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

## HTML examples

### Labels
#### Overview
* All form labels should have a for attribute that matches the id of the form element they are paired with
* If needing to overcome the one-to-one limitation for label and form element, than aria-labelledby should be used
* If additional (non-label) information is needed, then an aria-describedby attribute should be used; multiple elements can reference the same aria-describedby; aria-describedby should never replace the label, it should be used in addition to a label

#### Basic
```html
<label for="page-name">Page name</label>
<input type="text" name="page-name" id="page-name"> 
```

#### Required
```html
<label for="page-name">Page name <span aria-hidden="true">*</span></label>
<input type="text" name="page-name" id="page-name" required> 
```

#### Optional
```html
<label for="page-name">Page name (optional)</label>
<input type="text" name="page-name" id="page-name"> 
```

#### With aria-describedby
```html
<label for="page-name">Page name</label>
<input type="text" name="page-name" id="page-name" aria-describedby="page-name-validation"> 
<br>
<span id="page-name-validation">Page name may only include letters and numbers.</span>
```

### Checkboxes
```html
<fieldset>
  <legend>Video options</legend>
  <input id="publish" type="checkbox" name="asset-options" value="publish">
  <label for="publish">Publish after upload</label><br>
  <input id="generate-captions" type="checkbox" name="generate-captions" value="captions">
  <label for="generate-captions">Automatically generate captions</label><br>
</fieldset>
```

### Radio buttons
```html
<fieldset>
  <legend>Redirect type</legend>
  <input id="permanent" type="radio" name="redirect" value="permanent">
  <label for="permanent">Permanent redirect (301)</label><br>
  <input id="temporary" type="radio" name="redirect" value="temporary">
  <label for="temporary">Temporary redirect (302)</label><br>
  <input id="no-redirect" type="radio" name="redirect" value="no-redirect">
  <label for="no-redirect">No redirect (404)</label>
</fieldset>
```

### Select menu
```html
<label for="workflow-state">Workflow state</label>
<select id="workflow-state" name="select">
<option value="1">Created</option>
<option value="2">Reviewed</option>
<option value="3">Approved</option>
<option value="4">Rejected</option>
<option value="5">Annotated</option>
<option value="6">Retired</option>
</select>
```

## References
* [Webaim accessible form techniques](https://webaim.org/techniques/forms/)
* [Mozilla accessible HTML](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)