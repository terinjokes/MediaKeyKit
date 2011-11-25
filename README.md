# MediaKeyKit

Many applications want to your Mac's media keys. Unfortunately, there is no Apple approved method to do so, leading each to implement their own solutions, by either patching system libraries and applications or by playing a "trump card" and blocking out all other applications, or by telling their users to find their own way of fixing the problem.

**In the end**, either by confusion or annoyance, **the end users lose**. And no matter who you are, that's not good.

Of course, we're not all idiots. (though, one might argue that I am, my previous work on this problem implemented the trump method I've already blasted.) Some people, such as [nevyn/SPMediaKeyTap](https://github.com/nevyn/SPMediaKeyTap) have implemented ways to play nicer with other applications, but unfortunately his requires a hardcoded whitelist, which we both agree to be a subpar solution.

Originally I planned on using distributed notifications for this, but I've since been informed that distributed notifications are practically useless in sandbox applications. This leaves two possible solutions:

1. Using UDP
2. Using XPC

The problem with the first is that it requires network entitlements. While this isn't a problem for applications that already have that entitlement, it would still leave the other applications in the dust.

The problem with the second is that XPC is that is avialable in 10.7+. So I would still have to come up with some backwards compatiblity for 10.6 applications. In the long run, I do believe this is the best solution, and with code samples could be made pretty painless for end developers. Unfortunately, I don't have any previous with XPC, so the going might be tough.

Seems that in a sandbox, CGEventTap is useless. :|
