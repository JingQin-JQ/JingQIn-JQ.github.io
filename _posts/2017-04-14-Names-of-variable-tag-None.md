---
layout: post
title: Names of variable, tag, attribute and None
tags: 
- Python Study
---
Study notes about Python during access webdata

### "-" as a variable 
_ has 3 main conventional uses in Python:

* To hold the result of the last executed statement in an interactive interpreter session. This precedent was set by the standard CPython interpreter, and other interpreters have followed suit

* For translation lookup in i18n (see the gettext documentation for example), as in code like: raise forms.ValidationError(_("Please enter a correct username"))

* As a general purpose "throwaway" variable name to indicate that part of a function result is being deliberately ignored, as in code like: 

``` python
label, has_label, _ = text.partition(':')
```

* The latter two purposes can conflict, so it is necessary to avoid using _ as a throwaway variable in any code block that also uses it for i18n translation (many folks prefer a double-underscore, __, as their throwaway variable for exactly this reason).

### \<a\> tag

* The a tagtag defines a hyperlink, which is used to link from one page to another.

* The most important attribute of the \<a\> element is the href attribute, which indicates the link's destination.

* By default, links will appear as follows in all browsers:
   
   * An unvisited link is underlined and blue
   
   * A visited link is underlined and purple
   
   * An active link is underlined and red
  
### href Attribute   
* For \<a\> and \<area\> elements, the href attribute specifies the URL of the page the link goes to.

* For \<base\> elements, the href attribute specifies the base URL for all relative URLs on a page.

* For \<link\> elements, the href attribute specifies the location (URL) of the external resource (most often a style sheet file).

###  Attributes
* All HTML elements can have attributes

* Attributes provide additional information about an element

* Attributes are always specified in the start tag

* Attributes usually come in name/value pairs like: name="value"
   
### tag.get(key, None) how to understand None

* which will return None if key is not in tag. You can also provide a different default value that will be returned instead of None:
 
 ``` python
 value = tag.get(key, "empty")   
```

### Names of variable 
* The Rules

  * Variables names must start with a letter or an underscore, 
    
     * _underscore
    
     * underscore_
  
  * The remainder of your variable name may consist of letters, numbers and underscores. 
     
     * password1
    
     * n00b. ...
    
     * un_der_scores
  
  * Names are case sensitive. 
     
     * case_sensitive,  CASE_SENSITIVE, and Case_Sensitive are each a different variable.
    
  
* The Conventions
  
  * Readability is very important. Which of the following is easiest to read? I’m hoping you’ll say the first example.
    
     * python_puppet
    
     * pythonpuppet
    
     * pythonPuppet
 
  * Descriptive names are very useful. If you are writing a program that adds up all of the bad puns made in this book, which do you think is the better variable name?
     
     * total_bad_puns
    
     * super_bad
  
  * Avoid using the lowercase letter ‘l’, uppercase ‘O’, and uppercase ‘I’. Why? Because the l and the I look a lot like each other and the number 1. And O looks a lot like 0.
