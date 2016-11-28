---
title: "Write descriptive headings, not just descriptive links"
date: 2016-11-26
intro: Recently I was working on a project which had a big hero-component on almost every page. Initially I marked it up as an h1, until I found out that 99% of the time it was use to display a quote or some fancy marketing slogan. That made me reconsider the use of the H1-element.
lead: Recently I was working on a project which had a big hero-component on almost every page. Initially I marked it up as an h1, until I found out that 99% of the time it was use to display a quote or some fancy marketing slogan. That made me reconsider the use of the H1-element.
---

## Remember 'read more' links?
Remember when almost every site would have a ton of *click here* or *read more* links? People who were using assistive technology were having a hard
times using them, as those links were not describing what they were pointing to. Back in those days very few people cared about accessibility or
semantics, so not much was done to fix it. Until <abbr title="Search Engine Optimization">SEO</abbr> came along.

## SEO saves the day
When search-engines like Google came in the picture it became very important to build your website as good as possible to assure a good position in
the search results. In those early days search-engines mainly focused on the plain <abbr title="HyperText Markup Language">HTML</abbr> of a website - as did most assistive technology
in those days. So when companies thought they were just improving their websites for their PageRank, they were actually improving it as well for users of
<abbr title="Assistive Technology">AT</abbr>. A big step forward for semantic and accessible <abbr>HTML</abbr>!

## Marketing gets involved
As the web exploded, marketing and copywriters got more and more involved. Content is about the only thing on a website which is important, so it's
great that people who know about writing easy and pleasant to read content are involved. However, this also meant that *boring* but functional texts
like *Contact*, *News* and *Jobs* became *Stay connected*, *What we learned today* and *Do what you are good at*.

### Structure of a page

The structure of a simple one-page website might start looking something like this:

{% highlight html %}
<header>
    <h1>My Awesome Site</h1>
</header>
<section>
    <h2>What we learned today</h2>
    <p>...</p>
</section>
<section>
    <h2>Do what you are good at</h2>
    <p>...</p>
</section>
<section>
    <h2>Stay connected</h2>
    <p>...</p>
</section>
{% endhighlight %}

Now I'm not saying that those titles are bad per se. It's just that they are not as descriptive as they should be. This might result in people not
understanding them correctly. This is especially a problem for users who navigate your content using a screenreader. They can simply press the <kbd>H</kbd>-key
and get an overview of the headings on the page. What's clearer?

- News
- Jobs
- Contact

or

- What we learned today
- Do what you are good at
- Stay connected

I'm guessing most of you reading this would pick the 1st list, right?

### Search engines also profit!

Most of the time the `H1` and the `title` of a page will be the same. So those marketing texts might actually end up in search results as well. What would you click on when looking for a phone number?

<a href="#">Stay Connected - My Awesome Website</a>

Or

<a href="#">Contact - My Awesome Website</a>

I know which one I would click first. I think I've made my point? Now, how can we still be friends with the content writers and marketeers in our team, while also satisfying our need for clear headings?

## Solutions to the problem

As always, there are multiple ways to solve this problem. These are the solutions I could think of right now, but I'd <a href="/contact/">love to hear</a>
your thoughts on the matter!

### Group together in a parent element

Some of you might have thought about using the `hgroup`-element, right? When the <abbr>HTML5</abbr>-spec was introduced, an `hgroup`-element was introduced. The element was specifically created for headers with subheadings: <cite>
The hgroup element is typically used to group a set of one or more h1-h6 elements — to group, for example, a section title and an accompanying subtitle.</cite>
That might look something like this:

{% highlight html %}
<hgroup>
    <h2>Contact</h2>
    <h3>Stay connected</h3>
</hgroup>
{% endhighlight %}

However, <a href="http://lists.w3.org/Archives/Public/public-html-admin/2013Apr/0003.html">the element was removed from the spec</a> in early 2013. No worries, we can
just use a `header`-element, right?

{% highlight html %}
<header>
    <h2>Contact</h2>
    <h3>Stay connected</h3>
</header>
{% endhighlight %}

That's better. But why should that subtitle be a `h3`-element? It's not *really* a header, right? This way, people using headers to navigate would
still be confronted with non-descriptive headers. So it would probably be better to just use another element, like a `p`.

{% highlight html %}
<header>
    <h2>Contact</h2>
    <p>Stay connected</p>
</header>
{% endhighlight %}

Using <abbr title="Cascading StyleSheets">CSS</abbr> you can do as you please. You can make the `h2` small and the `p` a lot bigger, or use a bright color on the slogan/subtitle while
using a desaturated color on the `h2`.


### Visually hide the real title

If you really don't want to display the descriptive title, you might use a <abbr>CSS</abbr> utility/helper-class in your <abbr>HTML</abbr> to hide the
 contents of the element of screen, but still make them available to tools like screenreaders or search-engines. My former colleague <a href="http://rikschennink.nl">
 Rik Schennink</a> has written an excellent article about hiding this type of content, which he has named <a href="http://rikschennink.nl/thoughts/implicit-content-and-screen-readers/">implicit content</a>.
 A basic example would look like this:


{% highlight html %}
<header>
    <h2 class="visually-hidden">Contact</h2>
    <p>Stay connected</p>
</h2>
{% endhighlight %}

Or if you want the subheading to be included in the heading itself:

{% highlight html %}
<h2>
    <span class="visually-hidden">Contact: </span>
    Stay connected
</h2>
{% endhighlight %}

## Conclusion

Whatever solution you pick, keep in mind that the solutions outlined above do not only make your website easier to
understand and use for people using assistive technologies. They make them easier to use for *everyone*!