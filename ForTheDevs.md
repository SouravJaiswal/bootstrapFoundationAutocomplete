bootstrapFoundationAutocomplete
===============================
## Idea ##
Create an autocomplete feature in Sublime Text for Bootstrap and Foundations. *As a future goal* we could generalise the system of adding info-hovers, which can speed up creating support for (new) frameworks and languages among the SublimeText user-base.

**We are accepting suggestions for a better name for this repostiory.**

##Classes##
Classes in HTML are different from what you may have seen in other programming languages. In HTML , classes are used to group different tags together, so that you can do certain specific task with them.
	For example:
	If we have two div tags(division tags) and we want to apply the same style to them both, isn't it a better idea to define a single rule(in CSS we apply rules) for them, instead of applying same sets of rules on each and every item.

	There isn't a predefined list, we have to see their documentation and create our own list.
	Bootstrap: www.getBootstrap.com
	Foundation : www.foundation.zurb.com

### Specifics ###
An info-hover should appear above the selected class name displaying various details about the function when the *bound-key* is hit OR, add "our info" to the standard autocomplete-hover-box when typing a keyword that our plugin recognises.
We shall start with CSS, so the decsription will be available for `classes`

  + Where can we get description from? Our hints must conform to some *yet unkown standard*, they should be extracted from official documentation if possible.
    * CSS reference/API website
    * Manually creation of hints [Avoid]).
  + If we take the keybind approach,
    * How exactly does the user select the text, ie, when the *bound-key* is hit, do we look for a (partial?/complete?) selction OR the word preceeding the cursor?

## TODO ##
+ Read through both the [JavaScriptFunctionDefinition](https://github.com/asdf23/JavaScriptFunctionDefinition) and [AndyPython](https://github.com/agibsonsw/AndyPython)
+ [Extending SublimeText's AutoComplete](http://www.eladyarkoni.com/2012/09/sublime-text-auto-complete-plugin.html) tutorial (*bad quality*) shows how to define (and hence over-ride) the `on_query_completions()` method. 
+ A popup can be created in this way, [API link](http://www.sublimetext.com/docs/3/api_reference.html#sublime.View)
```
show_popup_menu(items, on_done, <flags>)  (returns None)
```
  * Shows a pop up menu at the caret(cursor), to select an item in a list.
  * `on_done` will be called once, with the index of the selected item.
  If the pop up menu was cancelled, `on_done` will be called with an argument of -1.
  * `items` is an array of strings.
  * `flags` currently has no option. Don't specify it, hence the function takes 2 args.