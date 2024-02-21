
# Chair's notes - 2024

## 2024-01-29

- Merged [#45][20240129_1] as today was the deadline for its review and no
  objections have been raised. Some concerns about workflow have been raised
  by @TallTed but were promptly addressed by @woutermont in
  [comment][20240129_2], which in turn was ack'ed by @TallTed with a +1.
- Sent out [new instance of chair's overview][20240129_3] to the mailing list.
  
[20240129_1]: https://github.com/w3c/WebID/pull/45
[20240129_2]: https://github.com/w3c/WebID/pull/45#issuecomment-1907606710
[20240129_3]: https://lists.w3.org/Archives/Public/public-webid/2024Jan/0041.html

## 2024-01-31

- Merged [#55][20240131_1] as it fixes an issue with [#45][20240129_1] that we
  had not foreseen (redundant runs of the BikeShed build process that were 
  polluting the commit history with too many CI commits). No deadline, I merged
  this one right away as it's just a fix to something that had been previously
  discussed and agreed upon.

[20240131_1]: https://github.com/w3c/WebID/pull/55

## 2024-02-05

- Merged [#52][20240205_1] as today was the deadline for its review, no
  objections have been raised and it has been reviewed and ack'ed by members of
  the group.
- Merged [#56][20240205_2] as today was the deadline for its review, no
  objections have been raised and multiple participants have contributed to it.
    - Note that @melvincarvalho might have a strong objection.
    - Note that @webr3 would rather we focus on creating new documents rather
      than iterating on the current ones. However, the majority of this group
      prefers the latter.
- Sent out [new instance of chair's overview][20240205_3] to the mailing list.

[20240205_1]: https://github.com/w3c/WebID/pull/52
[20240205_2]: https://github.com/w3c/WebID/pull/56
[20240205_3]: https://lists.w3.org/Archives/Public/public-webid/2024Feb/0004.html

## 2024-02-21

Merged [#60][20240221_1] as:
  
- Today was the deadline for its review.
- It's been reviewed / approved by multiple participants.
- It's been mentioned in multiple "chair's overview" emails.
- It implements the consensus on definitions as tracked in [#37][20240221_2].

I note that two strong objections had been raised by @melvincarvalho across
different threads, both in the mailing list and on GitHub. Both objections are
mentioned in [this comment][20240221_3]:

> I would prefer instead creating a serialization neutral definition of WebID
> which I believe has significant mind share in the group, and then to revisit
> this.

This is actually something that [#60][20240221_1] already addresses. The new
definitions [are neutral WRT serialization formats][20240221_4].

> As stated, I am in favour of a short freeze on the evolution of this document.

This has been addressed multiple times in multiple places,
[some by me][20240221_5] and [some by others][20240221_6].

As chair, I believe that both objections have been considered and addressed
adequately.

[20240221_1]: https://github.com/w3c/WebID/pull/60
[20240221_2]: https://github.com/w3c/WebID/issues/37
[20240221_3]: https://github.com/w3c/WebID/pull/60#issuecomment-1931572536
[20240221_4]: https://github.com/w3c/WebID/pull/60/files#diff-274f5e91238718e44b429797b66dcdc21e2d576ae2e0e769f0279840e5196945R195
[20240221_5]: https://github.com/w3c/WebID/issues/58#issuecomment-1925809369
[20240221_6]: https://github.com/w3c/WebID/issues/41#issue-2079076941
