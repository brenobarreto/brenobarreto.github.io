---
layout: post
title:  "Why people still use self-closing HTML tags like <br/>"
categories: weby-nuggets
excerpt: "XHTML has not been used for a long time, but a lot of people still use something inherited from it and completely ignored by browsers: self-closing tags."
---

HTML has two types of tags: 
- **Container tags**: the tags that need information inside. Because of that, you need to inform where the element starts and where it ends. For example, if you'd write a paragraph, you would type something lile `<p>Hello World</p>`, where `<p>` is the opening paragraph tag and `</p>` is the closing paragraph tag.  
- **Empty tags**: these are the ones that don't need any information inside. For example, in case you want to break a line, you just type `<br>`. There is nothing to be contained there, so you don't need a `</br>` (there is no such thing in HTML).

OK, pretty basic stuff.

And then we see all over the web things like `<br/>`. What the heck is that?

Note that the forward slash in this case is after the `br`, not before. This actually means `<br></br>`, which we've just that makes no sense. And it doesn't.

Self-closing tags like this come from the long-forgotten [XHTML](https://www.w3.org/TR/xhtml1/), which was an attempt raised by W3C to extend HTML using the syntax of **XML** rather than [SGML](https://en.wikipedia.org/wiki/Standard_Generalized_Markup_Language) - the original standard in which HTML was based. Until HTML5, there was still an attempt to define HTML as an SGML application, but HTML5 left that aattempt behind. (HTML4 was still defined by W3C as "an SGML application conforming to International Standard ISO 8879".)

The thing is XML is much more strict than HTML. For instance, if there is any error in an XML document, the entire document will simply not be rendered. Although there are advantages there, I can only imagine that a web based on XML would be constantly half broken. 

In its strictness, XML requires that every opening tag _must_ have a corresponding closing tag, no matter if it's a container or not. So you would write `<br></br>`, which can be abbreviated by using `<br/>`. Both mean the same.

HTML5 doesn't complain if it sees a self-closing tag like that, but only to keep compatibility. What actually happens under the hood is that the forward slash is ignored.