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

Final Form is starting with lifting.

Final form works by feeding video(s) of your form directly to our machine learning stack. For each lift you get a "baseball card" breaking down your lift.

LIFT 1
BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_bar_too_high.png){:height="700px" width="600px"}

Lift 1 FEED BACK:
Rep 1 :  Angle is too ...
Kind of Lift: Clean (93% confidence)
Overall score (Expert vs Novice): 20%(from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Bar to chest distance to large. Try to keep bar closer to body.

BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_elbow_too_low.png){:height="700px" width="600px"}

Lift 2 Feedback:
Kind of Lift: Clean (96% confidence)
Overall score (Expert vs Novice): 35 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Elbow to bar angle too wide at time 00:30 seconds. Try to bring your elbows up
Play back video ? [Yes/No]

BAD CLEAN w/ annotations
![My helpful screenshot]({{ finalform.com }}/downloads/clean_stance_too_wide.png){:height="700px" width="600px"}

Lift 3 Feedback
Kind of Lift: Clean (90% confidence)
Overall score (Expert vs Novice): 15 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Lower left leg , Lower right leg angle too wide. Try to bring your legs closer.
Play back video ? [Yes/No]

GOOD CLEAN w/annotations

![My helpful screenshot]({{ finalform.com }}/downloads/clean_perfect.png){:height="700px" width="600px"}

Lift 3 Feedback
Kind of Lift: Clean (98% confidence)
Overall score (Expert vs Novice): 80 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: No significant anomalies.
Play back video ? [Yes/No]

How does it work?

1. Capture 10 representative images. Vectorize using state-of-the-art neural net libraries such as VGG.
2. Use LSTM to classify lift.
3. Use gross body part identification to determine angles between gross anatomical features.
4. Use knowledge of the lift as well as example training data to determine these correct angles *as a function in time*.
5. Use image recognition of various plates as well as reading weight designation on plates to determine weight lifted.
6. Build a classifier trained to distinguish expert and novice lifters to get an overall score for a lift.



Segmentation example here:

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
