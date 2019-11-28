
# RxJS: Subjects, Behavior Subjects & Replay Subjects

> A subject in Rx is a special hybrid that can act as both an observable and an observer at the same time. This way, data can be pushed into a subject and the subject’s subscribers will in turn receive that pushed data.

`Subjects` are useful for `multicasting` or for when a source of data is not easily transformed into an observable. It’s easy to overuse subjects and oftentimes, as illustrated in this excellent post, subjects can be avoided when an observable source can be created otherwise.

On top of vanilla subjects, there are also a few specialized types of subjects like 
- Async subjects
- Behavior subjects
- Replay subjects.

Let's explore.



Using Subjects
Creating a subject is as simple as newing a new instance of RxJS’s Subject:

const mySubject = new Rx.Subject();
Multiple subscriptions can be created and internally the subject will keep a list of subscriptions:

const mySub = mySubject.subscribe(x => console.log(`${x} ${x}`));
const mySub2 = mySubject.subscribe(x => console.log(x.toUpperCase()));
Data can be pushed into the subject using its next method:

mySubject.next('👋 Hello!');

// 👋 Hello! 👋 Hello!
// 👋 HELLO!

https://alligator.io/rxjs/subjects/
