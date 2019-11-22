
# RxJS: Subjects, Behavior Subjects & Replay Subjects

> A subject in Rx is a special hybrid that can act as both an observable and an observer at the same time. This way, data can be pushed into a subject and the subject’s subscribers will in turn receive that pushed data.


Subjects are useful for `multicasting` or for when a source of data is not easily transformed into an observable. It’s easy to overuse subjects and oftentimes, as illustrated in this excellent post, subjects can be avoided when an observable source can be created otherwise.

On top of vanilla subjects, there are also a few specialized types of subjects like async subjects, behavior subjects and replay subjects. In this post, we’ll introduce subjects, behavior subjects and replay subjects.


https://alligator.io/rxjs/subjects/
