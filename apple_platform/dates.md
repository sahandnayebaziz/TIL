# iOS Dates

#### [How expensive is `DateFormatter`?](https://sarunw.com/posts/how-expensive-is-dateformatter/)

> The key take away from all these stats are:
>
> 1. `DateFormatter` is expensive to create.
> 1. `DateFormatter` is expensive to change.
> 1. Subsequent use of `string(from: Date)` is cheap.
> 1. Subsequent use of `date(from: String)` **is not** cheap.

#### [Wrangling Time: A Brief Explainer/Rant About Date Math](https://harshil.net/blog/foundation-date)

> This is slightly misleading, though. Despite what the preview shows, `Date` has no concept of days, months, years, any of that stuff. It deals solely with time, and more specifically, the number of seconds that have passed since midnight of 1 January 2001, in UTC.
>
> [...]
>
> Here’s a screenshot from the Health app, showing my step counts for the day of June 8, 2017. It was a fairly active day, as I got in a bit over 20,000 steps. The distribution of those steps, though, feels a bit off. It reads like I was up walking all night, and then asleep throughout the day, and scrolling around a bit, that’s the story for the rest of the week too. I don’t remember spending the week that way.
>
> As it happens I was in San Jose attending WWDC at the time, which has a -12:30 time difference with India , and as a result all of my health data from that trip appears time-shifted.
>
> [...]
>
> Going back to how `Date` works, it doesn’t model the actual clock time but rather a fixed point in time that can be interpreted in any time zone. And so what’s happening here is that the data is being interpreted as if it happened in my current time zone, which is the default time zone that `Calendar` and `DateFormatter` use.
>
> And as such, a `Date` alone isn’t sufficient for modelling historical data, or at least personal historical data: You need time zone information too.
