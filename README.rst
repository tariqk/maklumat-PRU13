=============================================================
 Results Information For the 13th Malaysian General Election
=============================================================

JSON data files for the 13th Malaysian General Elections (GE13).

Results obtained by scraping the `results page of the 13th Malaysian General Election`__, ripping it out of the HTML files, and then parsing it into JSON_.

__ http://resultpru13.spr.gov.my/
.. _JSON: http://www.json.org/

Why do it?
==========

Well, because of this_ article, which were intriguing, but offered no data so that ordinary people could download the data and do stuff with it. And I figured, what the heck, right? I had ``wget``, I had ``emacs``, I knew how to use regular expressions, and I really wanted to learn what it would take to make well-formatted JSON. So there you have it.

.. _this: www.themalaysianinsider.com/litee/sideviews/article/a-first-pass-at-the-ge13-results-thomas-pepinsky/

Plus, I find digging into reams and reams of text to extract data and trying to get it to fit into JSON... soothing. Well, okay, at least more soothing than listening to the fucking news. I mean, really, guys? Sigh.

Why not use the James Chong's Google Spreadsheets for `Parliamentary`_ and `State`_ results? Doesn’t that have all the data we need?
====================================================================================================================================

.. _Parliamentary: https://docs.google.com/spreadsheet/ccc?key=0AvJO-ZnwDjXmdFFzM2ZTam1ONWlROU1zejhFQnZCUFE
.. _State: https://docs.google.com/spreadsheet/ccc?key=0AvJO-ZnwDjXmdFFrbW9lT25STFh4WElST2kxeUFaMlE

Hey, good job for pointing out those links! (heh). 

Yeah, those offer the data on the elections on a tabular form, and I really recommend you go into that if you really just want to dive into the data without too much fuss. You can already find out a *lot* of things about this election from those figures, but by necessity, the tabulated form sacrifices some data — off the top of my head, they don’t include the name of the people who were contending, and data like whether they lost their deposit or not is not available.

The goal for this repository, on the other hand, is to preserve as much information as possible that is available on the Election Commission's website. So yes, it's in JSON, and yes, it's not as easy to extract tabulated data from this repo. But that's not the point.

So is this data verified and checked for errors?
================================================

Ah... no. Sorry. I'm too lazy.

I can at least guarantee that the JSON files *do* parse -- I ran it through ``cat << files >>.json | python -mjson.tool`` and confirmed that it parses -- as a result, the current JSON files are the pretty-printed results of the JSON parser provided with Python, so not only is it nicely indented, but as a side-effect, the keys are all alphabetically arranged-- wait, what, you didn't want them to be alphabetically arranged?

Oh. Sorry. >_>;;

So how, exactly, do I use this data?
====================================

Um, I guess you could ``load the data into R``__ or something. I really didn't give it a thought. 

__ http://stackoverflow.com/questions/2617600/importing-data-from-a-json-file-into-r

The nice part about it is that at least this data *is* uniform and you *can* at least manipulate it programmatically. Also, *in theory*, this dataset should be *less buggy* than it would have been if someone had typed in the data manually.

Please feel free to prove me wrong.

Okay, your data's got an error in it. What now?
===============================================

Hey, ``let me know``__! Log an issue in github, specify which part of the information is incorrect, or inconsistent. I've also provided me the raw HTML from the EC's website files that I used, as well as the URLs that I grabbed those files from as a reference, if you want it. Well, I *want* it, in case I need to backtrack and figure out what's wrong with the sources.

__ https://github.com/tariqk/maklumat-PRU13/issues

Or, even better, if you've made some changes to the data (say, by adding more information, fixing reams and *reams* of stupid errors I possibly made), then feel free to submit a pull request and help me get it fixed. Please note that I'm still new to this whole git and github thing, though, also, I am kind of busy and might not have the time to attend to these issues promptly. I will try, though!

I have more questions I want to ask!
====================================

Aiyo.

Okay, okay, you can send an email to pru13data.t-boy@xoxy.net. It's a spam-eater email, but I'll try to respond to it ASAP, and try to keep it as open as long as possible. Other than that I dunno lah.
