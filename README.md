# Shadowban FAQ

## Ban types

### Search ban
This type of ban causes your tweets to be hidden from the search results entirely, no matter whether the quality filter is turned on or off. This behavior includes hashtags as well. This type of ban seems to be temporally limited for active accounts.

### Thread shadowban
This is what is referred to as conventional shadowban as well. It comprises a search ban while threads are completely ripped apart by hiding reply tweets of the affected user to others. Everything will look perfectly normal to the affected user but many others will not be able to see reply tweets of the affected user at all. Reasons for this ban include behavior like excessive tweeting or following. Again, this type of ban seems to be temporally limited for active accounts.

### Quality filter discrimination (QFD)
QFD causes your tweets to be invisible within the latest section of the search, including hashtags, when the quality filter is turned on. Note that this quality filter is located on the search page, is turned on by default and will be reset for each search anew. It differs from the quality filter controlling your notifications.  
QFD was introduced on 15 May 2018 as part of Twitter's so-called [healthy conversation project](https://blog.twitter.com/official/en_us/topics/product/2018/Serving_Healthy_Conversation.html).

#### Does turning off the quality filter within my notification settings help?
The quality filter within your notification settings only controls the notification you receive. Turning it off is recommended and will cause you to see more notifications which you would not have received otherwise. However, turning it off will not cause your own tweets to be more visible.

#### How do I get into the QFD ban?
A lot of interaction with accounts affected by QFD will likely cause your account to be affected by QFD soon, too. The absence of personal misbehavior does not guarantee an account to be unaffected.

#### How do I get out of the QFD ban?
Several German Twitter users that were affected by QFD have been experimenting with an Arabic follow-back botnet. The botnet generated a lot of followers for those who followed some accounts from this botnet. By accumulating many new followers that were not affected by QFD, at least 30 accounts were able to escape this type of ban. This is a strong hint that guilt by association is a major concept of the classifying algorithm.

#### Is there a political bias?
The quality filter indeed seems to mainly affect conservative and right-wing accounts. Testing over 2,000 contacts of two German left-wing extremist accounts did not yield a single account affected by QFD that would not be considered politically right. Testing 509 Twitter accounts from German Members of Parliament yielded 14 affected accounts. All of them belong to the AfD, which is a German right-wing party.

#### Does it only affect hashtags and the search? Why is it so bad then?
We cannot tell whether the effects of QFD are limited to hashtags and the search. These are only the symptoms making the ban visible to us. It shows that Twitter is capable and willing to discriminate accounts with certain political opinions. Since shadowbanning is a very unethical way to silence people already, it is possible for Twitter to apply methods that are harder to detect. Think of more subtle ways of banning by limiting the share of followers who a user's tweets are shown to. This would be a censorship method that could only be detected collectively by their followers.


## Functionality of the tester

### Search ban
The Twitter search features several search modifiers. One of them is the prefix `from:` which allows to search for tweets from a specific user. For example, when checking whether the [@jack](https://twitter.com/jack) has a shadowban, we query the Twitter search for [from:@jack](https://twitter.com/search?f=tweets&vertical=default&q=from%3A%40jack&src=typd&qf=off) with the quality filter disabled. If we do not find any tweets although the user has tweeted in the past, the account is subject to a search ban.

### Thread shadowban
When the user has a search ban, the tester searches their profile for the latest tweet with at least one reply. It then visits the direct URL of the tweet and selects some reply tweet. Afterwards, the direct URL of the reply tweet is visited. If the tweet that the user replied to is not visible, the likelihood that the account is affected by a thread shadowban is very high.

### QFD
When you upload an image or link to an external page, Twitter generates shortlinks like [https://t.co/vRBIQq8NgF](https://t.co/vRBIQq8NgF). We first find a reference tweet using a combination of `from:` and `filter:` search modifiers. For example, [from:@jack filter:links](https://twitter.com/search?f=tweets&q=from%3A%40jack%20filter%3Alinks&src=typd) returns all tweets from [@jack](https://twitter.com/jack) containing a link. We simply pick one result tweet as reference tweet and extract the shortlink. We then query the Twitter search for the tweet using the search link with the quality filter turned on and off. If the reference tweet is found in both cases, the account is not affected by QFD. In case it is found only when the filter is turned on, it is affected.  
We chose this method because shortlinks are unique. Methodically, it does not differ from searching for text or a hashtag but the uniqueness of shortlinks is a technical advantage.

## What to do?
Please help raise awareness of this censorship. Many affected German users have started to include a red ❌ in their Twitter name. You can simply copy that symbol from here: `❌`

## Miscellaneous questions
### Is this tester restricted to the EU?
No. `.eu` was just a cheap top-level domain under which we found an appealing name for the site.
