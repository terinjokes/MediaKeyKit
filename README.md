# MediaKeyKit

Many applications want to your Mac's media keys. Unfortunately, there is no Apple approved method to do so, leading each to implement their own solutions, by either patching system libraries and applications or by playing a "trump card" and blocking out all other applications, or by telling their users to find their own way of fixing the problem.

**In the end**, either by confusion or annoyance, **the end users lose**. And no matter who you are, that's not good.

Of course, we're not all idiots. (though, one might argue that I am, my previous work on this problem implemented the trump method I've already blasted.) Some people, such as nevyn/SPMediaKeyTap have implemented ways to play nicer with other applications, but unfortunately his requires a hardcoded whitelist, which we both agree to be a subpar solution.

This is my attempt at creating a better, long term solution using distributed notifications.
