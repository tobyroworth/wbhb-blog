# Introduction #

So users don't have to wait for their next story to load, the next likely stories should be prefetched.

Similarly, read stories should be kept, when sensible, if they'll be re-read within the app lifetime

# Related Issues #

  * [issue 14](https://code.google.com/p/wbhb-blog/issues/detail?id=14)
  * [issue 5](https://code.google.com/p/wbhb-blog/issues/detail?id=5)

# User Considerations #

  * Most people will be reading the latest story, or one specific story, when they first visit the site
  * They may then read the next chronologically, or the next in a series ([issue 5](https://code.google.com/p/wbhb-blog/issues/detail?id=5)) (in either direction)
  * If a user accidentally scrolls (more likely if binding to scrollwheel), the page they've just read shouldn't need reloading
  * In the grid view, they might choose any story! Prefetching would be difficult - heuristics and statistics could take a guess (60% of people then read this etc)
  * As soon as a user clicks on the cover they expect it to be loaded - loading covers separate from pages has the risk of having a wait inbetween.

# Implementation Considerations #

GMail stores 5 messages in its cache - this may be a sensible number

Prefetching is network-intensive, so shouldn't be done too much

Story covers are required for the grid overview, so might be worth saving more rigorously than story content, which isn't likely to be read more than once.

Story covers are needed before the page content, but page content needs to be there immedietly.