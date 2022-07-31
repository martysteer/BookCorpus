# What the BookCorpus? 

So in the midst of all these Sesame Streets characters and robots transforming automobile era of "contextualize" language models, there is this ["Toronto Book Corpus"](https://yknzhu.wixsite.com/mbweb) that points to this [kinda recently influential paper](https://www.semanticscholar.org/paper/Aligning-Books-and-Movies%3A-Towards-Story-Like-by-Zhu-Kiros/0e6824e137847be0599bb0032e37042ed2ef5045?citingPapersSort=is-influential#citing-papers):

> Yukun Zhu, Ryan Kiros, Rich Zemel, Ruslan Salakhutdinov, Raquel Urtasun, Antonio Torralba, and Sanja Fidler. 2015. "Aligning books and movies: Towards story-like visual explanations by watching movies and reading books." In Proceedings of the IEEE international conference on computer vision, pp. 19-27. 

# Why do I even care, there's no translations there?

Some might know my personal pet peeve on collecting translation datasets but this BookCorpus has no translations, so why do I even care about it?

Partly because of https://twitter.com/jeremyphoward/status/1199742756253396993 , where Jeremy Howard asked where and what is this SimpleBook-92 corpus that papers and pre-trained models are using. 

> Does anyone know what the "simplebooks-92" dataset is, and where it can be found. It's mentioned on 
@gradientpub by  @chipro and also by @Thom_Wolf in a README, but neither has a link to a dataset with that name. Google doesn't show anything useful AFAICT

I spent the next 2 hours till near midnight searching high and low on the internet for this SimpleBook-92 too and it turns up empty. Then I start to think about the other datasets that created these autobots/decepticon models. And soon enough, the "BookCorpus" (aka. "Toronto Book Corpus") came under the radar. 

In my head, I thought wouldn't using Commoncrawl would have adhere to the normal laws of good and open research backed by [solid team of people that has access to laywer advice](https://commoncrawl.org/terms-of-use/). 

Thus, I start digging these "generalized" language models, partly for curiousity and for the sake of understanding how data is affecting the efficacy of the models. 

# Here comes the rabbit hole.

Giving up on the SimpleBooks, I start digging into the Toronto Book Corpus. Obviously the first thing is:

 > https://www.google.com/search?q=%22Toronto+Book+Corpus%22
 
Then somehow it pointed to a whole range of publications from openreview.net and BERTology papers from ACL anthology. Of course, not long after, I found the original source:

 > https://yknzhu.wixsite.com/mbweb
 
And under the data section of the page, there's this:

 > MovieBook dataset: We no longer host this dataset. You can find movies and corresponding books on Amazon.
 > BookCorpus: Please visit smashwords.com to collect your own version of BookCorpus.
 
Fine, let me read the paper first. The first thing that jumps at me is that next/previous sentence prediction task, "Ah-ha! I thought, it's skip-thought!! Then scrolled up the pdf and saw Kiros as one of the authors. Now I get it." Then, revelation, ah it's the same year publication. (P/S: I'm a big fan of the Skip-Thought paper, still.)

Okay, great, I understand the idea and what the authors are trying to achieve so what about the data? 

**Can we REALLY use book data that are not legitimately and openly available?**

But first, where the heck is the data? And in 2019, we still see people using the corpus to train their LMs or trying to extend or mess around models trained on the BookCorpus.

At this point, I went to Twitter and just posted: https://twitter.com/alvations/status/1204341588014419969

> Okay, we have to stop this madness on "Toronto Book Corpus" or "MovieBook Corpus". If it's no longer available, we should not continue to work on them. 
> 
> @aclmeeting and #nlproc community should REALLY be concern about datasets and how they're created and released...

# Where's Waldo?

After the initial Googling, my usual data archeological digging points me to the Way Back machine:

> https://web.archive.org/web/*/https://yknzhu.wixsite.com/mbweb

It looks like the oldest snapshot was in 2016 and a blank page came up and the [snapshot from 2019 May onwards](https://web.archive.org/web/20190521100304/https://yknzhu.wixsite.com/mbweb) points to the page with the note that data is no longer released. 

Now its serious... Why is "history" scrubbed on the way back machine? After a few more Googling for name of author, it points to:

- https://www.cs.toronto.edu/~yukun/
- https://www.cs.utoronto.ca/~fidler/
- http://www.cs.toronto.edu/~rkiros/
- http://www.cs.toronto.edu/~zemel/inquiry/home.php
- https://www.cs.cmu.edu/~rsalakhu/
- http://www.cs.toronto.edu/~urtasun/
- http://web.mit.edu/torralba/www/

Applying some social engineering, `yknzhu` must have referred to the first author in `https://yknzhu.wixsite.com/mbweb` so what's `mbweb`? Movie Book Web? 

Hence:

> https://www.google.com/search?q=mbweb+toronto

And it points to these:

 - https://github.com/ryankiros/neural-storyteller/issues/17
 - https://www.reddit.com/r/datasets/comments/56f5s3/bookcorpus_mirror/
 - https://twitter.com/rsalakhu/status/620000728191528960

And that GitHub link points to this ["build your own BookCorpus" repository from @soskek](https://github.com/soskek/bookcorpus) and ultimately asks users to crawl the [smashwords.com](https://www.smashwords.com/) site. 

Reflex action, search for "Harry Potter" in the smashwords site. 

> https://www.smashwords.com/books/search?query=harry+potter 

Ah, the `Harry Potter and the Sorcerers Stone` didn't show up, so the MovieBook corpus portion of the paper wouldn't be found on smashwords.com. Fine, that's just a minor distraction. 

So the question remains, **if these books are there and downloadable why can't we get them?**

Achso! thee's a price to each book!! So this is a self-publishing site, like the infamous [Amazon Kindle Direct Publishing](https://kdp.amazon.com). 

Okay, lets dig into the T&C or Terms of use:

> https://www.smashwords.com/about/supportfaq

-_-||| 42 A4 size pages of FAQ, I'll make do with ctr+f

Okay, so there's some details on "pricing":

> **How should I price my book?**
> 
> This is a personal decision for the author or publisher.  When you sell a book, you receive two benefits.  The first is you get a sale, which means you earn income.  The second benefit is that you gain a reader, and a reader is a potential fan, and a fan will search out and purchase your other books and future books.  A fan is also a potential evangelist who will recommend your book to their friends.  When examining these two benefits, the second - gaining a reader - is actually more important to your long term success as an author, especially if you plan to continue writing and publishing books.  Here are some considerations on price: 1. Your ebook should be priced less than the print equivalent. Customers expect this, because they know your production cost (paper, printing, shipping, middlemen) is less. 2.  Lower priced books almost always sell more copies than higher priced books.  For example, in our 2014 Smashwords Survey, we found that books priced at $3.99 sell three to four times more copies on average than books priced  over $9.99.  At $3.99, thanks to the higher volume, books (on average) earn the same or more than books priced at $10.00+, yet they gain more readers.  3.  The sweet spot for full length fiction is usually $2.99 or $3.99.  The best price for full length non-fiction is usually $5.99 to $9.99.  A longer book deserves a higher price than a short book. 4. Consider the value of your book to the customer. As self-publishing guru Dan Poynter notes in his Self Publishing Manual, for a customer to buy your book at any price, they must believe the value of the book is greater than the cost of the book. 5. Just as over-pricing can be bad, so too can under-pricing. Consider the likely market of your book, and the cost of competitive books, and then price accordingly. 6. A higher price is a double-edged sword. It implies potential value and worth, yet it can also price the customer out of purchasing it. Set a fair list price, and then consider using Smashwords coupons to let the customer feel like they're getting a discount on a valuable product.  7.  If you write series, price the first book in the series at FREE. We've found that series with free series starters earn more income for the author than series with a priced series starter.  Give it a try, you might be surprised!  8.  You can change your price at Smashwords at any time, so feel free to experiment (Apple usually updates same-day, others are generally 2-3 business days).  9.  There are multiple other factors that can influence how your potential readers judge your price.  Click here for an interview with Mark Coker where he examines other factors to consider.  Click here to learn how ebook buyers discover ebooks they purchase (links to the Smashwords Blog).  The Secrets to Ebook Publishing Success, our free ebook that examines the best practices of the most successful Smashwords authors, also explores different strategies for pricing.

Heh, if this is a business, it means paid E-books? Then BookCorpus uses paid Ebooks and redistributed them? 

Time to re-read the paper, and so:

> **The BookCorpus Dataset.** In order to train our sentence similarity model we collected a corpus of 11,038 books ***from the web***. These are __**free books written by yet unpublished authors**__. We only included books that had more than 20K words in order to filter out perhaps noisier shorter stories. The dataset has books in 16 different genres, e.g., Romance (2,865 books), Fantasy (1,479), Science fiction (786), Teen (430), etc. Table 2 highlights the summary statistics of our book corpus.

Okay, so the BookCorpus distributed __**free ebooks**__, then why not continue to re-distribute them? Restrictions from smashwords site?

So anything here, would be technically free, right?:

> https://www.smashwords.com/books/category/1/newest/0/free/any 

At this point, I'll need to put up a disclaimer. **"I am not a lawyer"**. 

Looking into one of the "free ebook" link, `https://www.smashwords.com/books/view/88690`, it seems to point to Amazon where the book is sold in physical form: https://www.amazon.de/How-Be-Free-Joe-Blow/dp/1300343664 and also on [lulu.com](http://www.lulu.com/shop/http://www.lulu.com/shop/joe-blow/how-to-be-free/paperback/product-21982654.html).


Then I'm totally confused:
 
  - The BookCorpus is made of free ebooks (but there's a chance that the pricing changes so the ebook could be technically not free when printed)
  - The BookCorpus (in the publication) is said to be crawled from ***"from the web"***
  - And later on the project page, people were referred to smashwords.com to make their own BookCorpus
  - Also, forks of project has attempt to build crawlers like https://github.com/soskek/bookcorpus (also, a colleague told me that another similar crawler: https://towardsdatascience.com/replicating-the-toronto-bookcorpus-dataset-a-write-up-44ea7b87d091) 
  
So the question remains, why was the original BookCorpus taken down? **Can I still find it on the internet?**

Also, back to the MovieBookCorpus, actually this is where the gem lies, someone went to map the movie subtitles to the book and these annotations are also missing from the literature and the world.

I fired up one of the crawler and tried my luck at re-creating the book corpus and got only a couple of thousands out of 11,000 books and the rest of the requests got 500 errors. I guess my purpose was never to get the dataset. Then I thought, someone must have already done this completely so **why exactly are everyone else trying to repeat this crawling?**. 

# Where in the world is Carmen San BookCorpus?

Okay, lets try some more searching, this time in GitHub:

> https://github.com/search?q=bookcorpus

And this issue came up:

 > https://github.com/fh295/SentenceRepresentation/issues/3
 
Where there's a comment on:

 > I managed to get a hold of the dataset after mailing the authors of the paper, and I got two files- books_large_p1.txt and books_large_p2.txt. The code however refers to a books_large_70m.txt. Is that just the result of concatenating the two files? I'm trying to reproduce the results of the paper...
 
Hmmm, there's a distribution of the BookCropus where it's split into two files:

 - books_large_p1.txt
 - books_large_p2.txt
 
First thought, search `books_large_p2.txt` on Github:

 > https://github.com/search?q=books_large_p1&type=Code
 
Finally, I found the source but HORRORS of HORRORS... I've found the distribution that contains the two `.txt` files, compressed in `books_in_sentences.tar`.

This is NO way how we as a community should be distributing data and surely not in this unsafe manner. It involves passwords and usernames and wget unencrypted and put up on Github bash scripts =( 

Now what?
====

Okay, so I've found the BookCorpus, I did a count `wc -l` and looked at what's inside `head *.txt`. First I'm seriously not impressed by the fact that the data was already lowercased and seemed tokenized. Beyond that, I think we need to start rethinking how we treat datasets/corpora in NLP.

### How to choose what dataset to use? 

 - **Relevance**: Definitely the dataset needs to suit the task and purpose of the research
 - **Balance**: How well does the data cover the phenomenon or research topic? Usually this part is well described in the publication.
 - **Representation**: What is the representation of the data? How much can we really trust self-publications? What kind of bias it contains? See https://www.aclweb.org/anthology/Q18-1041.pdf
 - **Availability**: But beyond all that, we need to ask, can we distribute the data? What license would the (re-)distribution of the corpus be? Would it end up in another BookCorpus rabbit hole where it disappears? 
    
    
Similar considerations above should be made when creating a new dataset. 
    
    
### How to distribute datasets? 
 
 - Meta data on the datasets should be complusory, esp. when it comes to this age where data is massive and no one really knows how exactly something is crawled/created/cleaned.
 - Datasheet is a brill-ing good idea! See https://www.microsoft.com/en-us/research/uploads/prod/2019/01/1803.09010.pdf
 - What happens if cease and deceased happens? This part, disclaimer again, **I am not a lawyer**. Replicating steps to recreate the dataset is good. But seriously, __the original authors should give a reason why the data is taken down__. Otherwise, replicating the dataset creation is just going to cause another ceased or deceased situation... And if there's really nothing wrong with re-distribution, then the replication blogpost/papers/repos should attempt to re-distribute the data. 
 - NEVER EVER put up usernames and passwords to account, unless that account is really rendered as useless. In this case, for the benefit of doubt, I'll assume that the user/pass found to get the `books_in_sentences.tar` is really a useless dummy account. 
    
### What should we do with all these papers using BookCorpus?

 - I don't have a clue... As a community, we really need to decide together to stop using something that we can't or the original authors won't re-distribute. Perhaps after replicating the BookCorpus from one of the crawlers we should just move on and use those new replicas. 
 
 - There are soooo many other corpus of similar size for English, I think as a researcher, we can surely choose a better corpus that is truly available without this where's waldo search -_-|||
    - Common Crawl is a good one https://commoncrawl.org/
    - Gutenberg too: https://www.gutenberg.org/
    - And I'm sure if we look hard enough, there's a tonne more... 
    - Also, we should really go beyond English for all these models... Original BookCorpus seems to be made up of just English books...
    
 - What about comparability? Wouldn't my language model or novel idea not be comparable? 
   - Don't kid ourselves, we really don't care what the model is trained more than how we tests them, as long as the bench mark, Squad, Glue or whichever future acronym test set exists, the work is comparable. 
   - And if we stop using datasets that are not available, it's actually makes future work more comparable
   
 - Then should we just all retrain these pre-trained models using datasets that are available and ditch the models trained on BookCorpus? Yes, I personally think it's the best scenario but that's my only my own opinion. It's how we think and work as a community that really matters. 
   
I apologize for the above if it seems like a rant and I am definitely not attacking or saying that the authors of the BookCorpus is wrong in taking the data down for some reason. But I think as a community, we really need to rethink how we create and choose datasets. Esp. in this age of "transfer-learning" where our models are "inheriting" information from pre-trained models and the original source of the data for these pre-trained models are no longer available. 
    
    