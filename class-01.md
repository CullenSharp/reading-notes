# Introductory HTML and JavaScript

Notes from code201 reading 1 (3.8.21)

----

## HTML, CSS, Intro

HTML (hypertext markup language) is the bones of the webpage. This is where you define the core elements, but not their layout, style or interaction. HTML5 is the current version of this language.

CSS (cascading style sheets) is the styling and layout. Typically done near the end of development, CSS is how you make everything look right. CSS3 is the current version.

*Browsers* - Software that allows users to access and render websites.

*Web server* - the server hosts the website's core files. When a user requests a file, it comes from the server to them. 

*ISP* - Internet service provider, this is the company that provides you with access to the internet.

*DNS look up* - Domain name system look up is the process by which a domain name is checked, and its affiliated page requested.

----

## Structure, 1

Structure is how you use HTML to organize a pages content. Typically, the developer or designer does so in an ergonomic fashion; information which is high level, or pertinent to the user, is quick and easy to find. But structure changes with every application. A newspaper will probably look very different from a tax return website, and this can be a local thing too. You might need a radically different structure on a login page than on a main page. Still the primary elements are visual hierarchy and ergonomics.

HTML does structure in a very explicit way... well it can be a little loosey. Nonetheless you structure a site with semantic tags: head, body, header, nav, section, article, etc. These specific tags don't render anything, but tell us what's whould be inside that element. For instance the bulk of our information will be in the main section. Navigation and headlines might be in the header or footer, and the head contains all the meta data. 

On a more mirco level, an HTML tag is composed of 4 core components, an opening tag, attribute(s), content, and a closing tag. Take a look at this one:

````HTML
<p class="hello"> hello world </p>
````

The first 'p' with brackets is the opening tag. The class is an attribute... later, we can use this to select it. 'hello world' is our content, and the final 'p' tag closes everything and completes the *element*.

Sometimes you won't have to write any of this code. For that you use a CMS (Content Management System). This is the system you use when on those 'website builder' sites. It comes with themes and basic design options, and streamlines the  process significantly. With this setup, you can very quickly get into building and make style choices on the fly.

----

## Extra Markup, 8

A brief history, HTML 4 (released 1997) the majority of elements that make up today's web are from HTML 4. Not coinicidentally, the arrival of HTML 4 is also seen as the entrance of a new era of web design: web 2.0.

With XHTML 1.0 (2000), HTML picked up some rules from XML. It became more strict. Now closing tags were required, attribute names became lowercase, etc..

HTML 5 (current) is still a work in progress, but it's elements are already in common use. It should be assumed that it is stable.

### Examples

````HTML
<!DOCTYPE html>
````

This doctype tag tells the browser which version of HTML the document is using.

````HTML
<!-- im a comment -->
````

A comment is a line of code that doesn't get run. They're useful for... comments, but also debugging code.

````HTML
<p class="1">hello</p>
<p id="2">hello</p>
````

A class and id attribute are used for indenifying elements in a page. They're useful for selecting elements you want to style in css. You could use a class to characterize a whole section, then have an id identify a specific element. You then use them in conjunction to apply styling rules to the effect elements. The virtue of this method is that every child of the parent element would inherit the rules of the parent, and then you can use the id to give even more specific rules to individual children. 

### Block elements and inline elements

This is easy. A block element starts a new line in the document, and an inline element doesn't.

It's not encouraged anymore, but you can group elements as a block with 'div' and inline with 'span'. It's not advised because as elements they don't describe themselves.

### Meta tags

Meta tags are elements that don't render in the page, but are readable to the browser and give details about the site.

````HTML
<!DOCTYPE html>
<html>
    <head>
        <title> My example </title>
        <meta name="description"
            content="I'm an example"/>
        <meta name="keywords"
            content="I, am, an, example"/>
        <meta name="robots"
            content="nofollow"/>
        <meta http-equiv="author"
            content="my name"/>
        <meta http-equiv="pragma"
            content="no-cache"/>
        <meta http-equiv="expires"
            content="Mon, 08 Mar 2021 23:59:59 GMT"/>
    </head>
</html>
````

*Description* is just that. Usually 155 chars. max, these describe the page to the browser's search engine.

*Keywords* is a list of comma seperated keywords the user might use on the site.

*Robots* tells the search engine whether or not the site should show up.

*Author* is the author's name.

*Pragma* determines whether or not the site gets cached to local memory.

*Expires* determines when the page expires from the cache.

----

## HTML5 Layout, 17

In this chapter we go over the new tags and elements introduced with HTML5.

The widespread use of 'div' to characterize *and* group content has been deprecated. Now we get cool semantic tags like header, nav, article, section, aside, footer. We'll go over the few which aren't self-evident. 

* *Article* is used to reference stand-alone content that can be syndicated

* *Aside* denotes information which is related to the article but not essential. For example, you could use it for a sidebar.

* *Section* is meant to group related content within an article, aside, etc.. Each section may have its own heading

* *hgroup* stands for header group; use it to group headers together, like say if you had a section header then a subsection header beneath it.

* *Figure and figcaption* figures are the main thing on display in an article or section. Use this tag to identify them and give them captions.

* *Div*, you come back to div for grouping elements which the new tags can't describe: the entire body for instance.

### Older browsers

Older browsers will not recognize the new tags as block elements, so in the css style as block elements like this:

````CSS
header, section, footer, aside, figure, figcaption, nav, article {
    display: block;
}
````

----

## Process and Design, 18

Every site is designed with a target audience in mind, but who they are and what they want may not be clear. It's important when starting out to create this audience and think about their needs, goals, and routes. This way you can effectively organize and structure your site such that it suits them. This information will also guide the entire process of designing the site.

Then once you have the user in mind (note it can be helpful to actually ask them), you can begin to map the site out. Think of page groupings and create and ergonomic route for the user. This is basically just a sketch and can be done with paper cards. Think what will this user need to navigate this screen, and where should they go after. What makes sense if I were them?

You wireframe next; this is really just about getting everything on paper more or less. Nothing is set in stone at this stage, but it should be clear to people what the basic structure will be.

----

# JavaScript

## The ABCs of Programming, 1

A script is a set of programmatic instructions for the computer to follow. Some can be very complex and asynchronous, others can be low level and immediate. At either scale it's important to be logical and *very* explicit; don't allow the computer any chance to mess up.

You can write a script in three steps:

1. Define the goal
2. Design the script
3. Code each step

Break the entire action into individual steps. Think about them in a yes/no manner.

You have to give the computer the data it needs to define things. It doesn't know how to categorize anything without the proper parameters, so in essence you have to teach it to see.

You descibe things as objects with attributes and values: Person, Name: name, age: 24, gender: m... and so on.

Objects are interacted with through events. Say when I check into a hotel is an event that updates the vacancy of said hotel. Then that value triggers a whole slew of operations. Operations are called methods. Basically, they are functions contained within objects.

### Writing a script for a webpage

Work in increments: HTML, CSS, JS (first the stucture, then the looks, then the interaction). Each of these things are contained in seperate files and linked within the html document's head. This ensures clarity and modularity.