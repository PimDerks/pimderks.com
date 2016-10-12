---
title: "Tips for using an icon font"
date: 2016-10-12
intro: The use of icons can be great additions to the look and feel of your website or app. However, there are some things to keep in mind when using icon fonts!
lead: The use of icons can be great additions to the look and feel of your website or app. However, there are some things to keep in mind when using icon fonts!
---

## Don't use an icon font

Various
[articles](https://medium.com/@webprolific/why-and-how-i-m-using-svg-over-fonts-for-icons-7241dab890f0#.hn8tskn9j)
[have](https://css-tricks.com/icon-fonts-vs-svg/)
[been](https://nucleoapp.com/how-to-create-an-icon-system-using-svg-symbols/)
[written](https://sarasoueidan.com/blog/icon-fonts-to-svg/)
about how and why and you should use <abbr title="Scalable Vector Graphics">SVG</abbr> instead of an icon font, so I'm not going to waste any time on that. If you have the choice to use <abbr>SVG</abbr>, you can probably stop reading this article.
However, you might have your own reasons for still using them or you may be working in a legacy project which uses them. Here are some tips to keep in mind when using good ol' icon fonts.

## Use a separate node

I prefer to have a separate node for each icon. Don't do something like this:

{% highlight html %}
<button type="button" class="icon icon-ok">Confirm</button>
{% endhighlight %}

Try this instead:

{% highlight html %}
<button type="button">
    <span class="icon icon-ok"></span>
    Confirm
</button>
{% endhighlight %}

Having a separate node for your icon will allow you to interact with the icon a lot easier, especially
if you need to target the icon in JavaScript of if you want to enhance the accessibility of your website.
Talking of which...

## Hide the icon for assistive technology

People with poor or none eyesight will probably use a screenreader to navigate your website. Most screenreaders
will read out CSS generated content as well. As most implementations of icon-fonts use generated content
 to display an icon, this icon will be read out as well.

In the best case scenario, this will result in for example <cite>q search</cite> being read out. However a lot of icon-fonts
by default use obscure foreign characters to map their icons to. As most screenreaders do not support these
characters, this will result in the user being informed that the label of the button is <cite>undefined search</cite>.

By using the ARIA-hidden attribute you can inform assistive technologies to hide the element.
Great, we've just put our icon in its own separate node, so we can do that really quick!

{% highlight html %}
<button type="button">
    <span class="icon icon-ok" aria-hidden="true"></span>
    Confirm
</button>
{% endhighlight %}

## Provide a textual fallback for your mystery meat

I don't recommend using icons without a label to accompany them. There are a few reasons for this:

1. People may not understand icons (correctly). For older people like us (sigh) it might be very clear
that an icon of a floppy disk means 'Save'. For people who never actually *used* a floppy it probably won't.
2. Icons and colours might have a different meaning in another language or culture.
3. Icons/fonts may not load (error, CSS disabled).
4. Icons/fonts may be blocked (content blockers).

However, if you insist on having no visual label available to the user, there are still ways to make it available to assistive technology, for example by using the <code>aria-label</code> attribute:

{% highlight html %}
<button type="button" aria-label="Confirm">
    <span class="icon icon-ok" aria-hidden="true"></span>
</button>
{% endhighlight %}

This is not a rock-solid though, as people **not** using a screenreader will still have to deal with an empty button when the icon doesn't appear.

## Conclusion

Icons can be a great addition to your <abbr>UI</abbr>. Just keep in mind that there are tons of reasons why icons
may not show up. Make sure your interface can still be used when that happens!
