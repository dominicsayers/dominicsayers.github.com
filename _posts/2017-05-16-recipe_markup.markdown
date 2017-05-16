---
layout: post
title: Using Jekyll to markup a recipe
date: 2017-05-15 16:00:00 +0000
image: recipe.png
thumbnail: recipe.png
tags: featured
---
I wanted to share my no-weighing flapjack recipe with the world so I added [a post](/flapjack/) last month.

Before I published it I researched how to mark up the HTML so that Google knew it was a recipe rather than just a bit of text. Turns out there's a reasonably mature [markup schema](http://schema.org/Recipe) that [Google uses](https://developers.google.com/search/docs/data-types/recipes) to show recipes differently in its search results.

Here's how my recipe looks on Google:

![Flapjack recipe](/assets/article_images/recipe_markup/recipe.png)

As you can see, Google shows the preparation time as well as the calorific content and the star rating. This is because the post I created has the proper markup for a recipe.

I wanted to be able to do this easily for any [other recipes](/chocolate_mousse/) I posted in the future, so I created a template that ensures that all the recipe elements are marked up correctly.

To add a recipe using this template, the recipe elements (ingredients and method for example) need to be added to the page as [Front Matter](https://jekyllrb.com/docs/frontmatter/) (YAML) rather than just text.

I tried to make this easy and human-readable. Here's the flapjack recipe as data:

```YAML
---
ingredients:
  porridge oats: 1kg
  condensed milk: 400g
  soft brown sugar: 500g
  butter: 500g
instructions:
  - Preheat the oven to 150C fan.
  - Line a large baking tin with baking parchment (my tin measures 39cm x 26cm).
  - Melt the butter and sugar in a large pan over a low heat. Don't cook the butter, just warm it enough to melt it.
  - Remove the pan from the heat and stir in the condensed milk.
  - Mix in the oats until well coated by the mixture.
  - Pour into the baking tin and smooth out with the back of a large spoon.
  - Cook for about 15-20 minutes. When the flapjack starts to brown around the edges of the tin, take it out of the oven - it should still be relatively pale in the middle.
  - Leave to cool for a few minutes before cutting into pieces.
calories: 10547
prepmins: 20
cookmins: 15
layout: recipe
title: Moist flapjack with condensed milk
date: 2017-04-21 08:00:00 +0100
image: flapjack.jpg
thumbnail: flapjack.jpg
tags:
  - featured
  - recipe
---
This recipe makes enough flapjack for two hungry children for several weeks of school lunches.
```

To translate this front matter into HTML I created [a simple layout](https://github.com/dominicsayers/dominicsayers.github.com/blob/master/_includes/recipe_content.html). You should be able to adapt this for your own recipes.

{% highlight liquid %}
{% raw %}
<!-- recipe post-content -->
<div class="post-content">
  <div class="post-reading">
    <span class="post-reading-time"></span> read
  </div>

  <!-- ingredients -->
  <div>
    <h3>Ingredients</h3>
     <ul>
        {% for ingredient in page.ingredients %}
        <li itemprop="ingredients">{{ ingredient[1] }} {{ ingredient[0] }}</li>
        {% endfor %}
     </ul>
  </div>
  <!-- ingredients -->

  {{content}}

  <!-- instructions -->
  <div itemprop="recipeInstructions">
    <h3>Instructions</h3>
    <ol>
      <li>{{ page.instructions | join: '</li> <li>' }}</li>
    </ol>
  </div>
  <!-- instructions -->
</div>

{% if page.prepmins or page.cookmins %}
  <dl class="dl-horizontal">
    {% if page.prepmins %}<dt>Preparation time</dt><dd>{{ page.prepmins }} mins<span itemprop="prepTime" class="invisible">PT{{ page.prepmins }}M</span></dd>{% endif %}
    {% if page.cookmins %}<dt>Cooking time</dt><dd>{{ page.cookmins }} mins<span itemprop="cookTime" class="invisible">PT{{ page.cookmins }}M</span></dd>{% endif %}
  </dl>
{% endif %}

<p class="invisible" itemprop="description">{{ page.excerpt | strip_html | strip_newlines | truncate: 200 }}</p>
<p class="invisible" itemprop="nutrition" itemscope itemtype="http://schema.org/NutritionInformation"><span itemprop="calories">{{ page.calories | default: 2 }}</span></p>
<p class="invisible" itemprop="aggregateRating" itemscope itemtype="http://schema.org/AggregateRating"><span itemprop="ratingValue">5</span><span itemprop="reviewCount">1</span></p>
<!-- recipe post-content -->
{% endraw %}
{% endhighlight %}

Boom! Now I can add recipes easily and quickly.
