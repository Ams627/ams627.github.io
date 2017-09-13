---
layout: post
title:  "XAML Inline Syntax vs Object Element Syntax"
date:   2017-09-13 23:08:15 +0100
categories: jekyll update
---
XAML Inline syntax involves setting a property of an element using an XML attribute as follows:

{% highlight xml %}
<ListBox ItemTemplate="{StaticResource PathVisualTemplate}"/>
{% endhighlight %}

XAML Object Element Syntax is used to set more complex properties - for example to set a context menu on a ListBox:

{% highlight xml %}
<ListBox>
    <ListBox.ContextMenu>
        <ContextMenu>
            <MenuItem Header="Press this"/>
            <MenuItem Header="Press that"/>
        </ContextMenu>
    </ListBox.ContextMenu>
</ListBox>
{% endhighlight %}

However, it is perfectly possible to use Object Element Syntax whereever inline syntax is used:

{% highlight xml %}
<ListBox>
    <ListBox.ItemTemplate>
        <StaticResource ResourceKey="PathVisualTemplate"/>
    </ListBox.ItemTemplate>
</ListBox>
{% endhighlight %}
This is ill-advised for a simple example such as the one above since inline (XML attribute) syntax is shorter and
much clearer.

