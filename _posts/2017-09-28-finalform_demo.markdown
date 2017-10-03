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

We approximate the body as a (semi) rigid body. This means by keeping track of the angles between various body parts at different points in time we can determine what constitutes perfect form. We also use neural nets trained to distinguish expert lifters from novices to give an overall performance score.

**Final Form is starting with lifting. We want to short-cut countless hours of video review and uneven coaching.**

Final form works by feeding video(s) of your form directly to our machine learning stack.
**For each lift you get a "baseball card" breaking down your lift.**

LIFT 1
BAD CLEAN w/ annotations:
![My helpful screenshot]({{ finalform.com }}/downloads/clean_bar_too_high.png){:height="700px" width="600px"}

Lift 1 FEED BACK:
Kind of Lift: Clean (93% confidence)
Overall score (Expert vs Novice): 20%(from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Bar to chest distance to large at 00:35. Try to keep bar closer to body.

Lift 2 BAD CLEAN w/ annotations:
![My helpful screenshot]({{ finalform.com }}/downloads/clean_elbow_too_low.png){:height="700px" width="600px"}

Lift 2 Feedback:
Kind of Lift: Clean (96% confidence)
Overall score (Expert vs Novice): 35 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Elbow to bar angle too wide at time 00:30 seconds. Try to bring your elbows up.
Anomaly Detection: Elbows pointed towards ground at time 00:30 seconds. Try to catch clean with higher elbows.
Play back video ? [Yes/No]

Lift 3 BAD CLEAN w/ annotations:
![My helpful screenshot]({{ finalform.com }}/downloads/clean_stance_too_wide.png){:height="700px" width="600px"}

Lift 3 Feedback:
Kind of Lift: Clean (90% confidence)
Overall score (Expert vs Novice): 40 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: Lower left leg , Lower right leg angle too wide at time 00:20. Try to bring your legs closer.
Anomaly Detection: Stance and lower left leg and lower right leg angle too wide at time 00:40. Land with feet closer and a slightly more narrow foot angle.
Play back video ? [Yes/No]

Lift 4 GOOD CLEAN w/annotations:

![My helpful screenshot]({{ finalform.com }}/downloads/clean_perfect.png){:height="700px" width="600px"}

Lift 4 Feedback:
Kind of Lift: Clean (98% confidence)
Overall score (Expert vs Novice): 80 % (from 0 to 100)
Weight Lifted: approximately 60 kg / 135 pounds
Anomaly Detection: No significant anomalies.
Play back video ? [Yes/No]

How does it work?

1. Capture 10 evenly spaces images of each video. Vectorize using state-of-the-art neural net libraries such as VGG.
2. Use LSTM on the sequence of vectors to classify lift.
3. Use gross body part identification to determine angles between gross anatomical features. This is a different net that classifies each pixel as  head/neck, torso , left lower arm , left upper arm , left lower leg, and left upper leg, left hand, as well as the right-side version of all body parts that come in pairs.
4. Use knowledge of the lift as well as example training data to determine these correct angles *as a function in time*.
5. Use image recognition of various plates as well as reading weight designation on plates to determine weight lifted.
6. Build a third net/classifier trained to distinguish expert and novice lifters to get an overall score for a lift.



Segmentation example here:

![My helpful screenshot]({{ finalform.com }}/downloads/clean_segmentation_example.png){:height="800px" width="2000px"}

You see the head/neck area in gray, the torso in yellow, and the legs in green. This is a work in progress.
