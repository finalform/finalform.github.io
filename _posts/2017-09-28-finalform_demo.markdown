---
layout: post
title:  "Final Form Demo"
date:   2017-09-28 22:11:35 -0400
categories: jekyll update
---
<script type="text/javascript"
    src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

Achieving good form in sport means you can lift weights you couldn't lift before, make shots you couldn't make before, and sink puts you couldn't sink before.

We approximate the body as a (semi) rigid body. This means by keeping track of the angles between various body parts at different points in time we can determine what constitutes perfect form. We also use neural nets trained to distinguish expert lifters from novices to find

You go in and perform the sport of choice:

LIFT 1
BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_bar_too_high.png){:height="800px" width="600px"}

Lift 1 FEED BACK:

Lift 2 feedack
BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_elbow_too_low.png){:height="800px" width="600px"}


BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_stance_too_wide.png){:height="800px" width="600px"}

GOOD CLEAN w/annotations

![My helpful screenshot]({{ finalform.com }}/downloads/clean_perfect.png){:height="800px" width="600px"}


FINAL FORM REPORT CARD:


Rep 1 :  Angle is too ...
Kind of Lift:  
Overall score (Expert vs Novice):
Weight Lifted:

Rep2
Kind of Lift:
Overall score (Expert vs Novice):
Weight Lifted:

Rep 3:
Kind of Lift:
Overall score (Expert vs Novice):
Weight Lifted:

PUT a lift type classifier plot here!!
Explain how you use vgg!!!

Explain how you compute angle between line segments representing body parts!!!!

![My helpful screenshot]({{ finalform.com }}/downloads/clean_segmentation_example.png){:height="800px" width="2000px"} you see


We will discuss machine learning, physics: \\( sin(x^2) \\) , and provide some  `code` contributions.

$$ e^2 $$

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
