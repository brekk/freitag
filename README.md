# freitag 

ad-hoc, nestable, relatable tags


[![Madlib Project Badge](https://img.shields.io/badge/madlib-purple?logo=github&logoSize=auto)](//github.com/madlib-lang/madlib) <!-- $MADLIB.projectBadge -->
[![freitag v3.0.0](https://img.shields.io/badge/v3.0.0-purple?label=version)](//github.com/brekk/freitag) <!-- $MADLIB.json.version -->

---

Tags are lightweight wrapper around a list of strings. `Tag(["a", "b", "c"])` Tags are meant to be automatic left-sorting, so `Tag(["a", "b"])` is naturally sorted as lesser than `Tag(["a", "b", "c"])`.

The `Tagged` type allows you to associate multiple tags with tag queries. This enables granular filtering. The user must define their request by highest specificity first, as earlier general matches will void later ones. `!flora:photosynthesis,flora:*,fauna:creature:*,ecosystem:*` can express `InvertTag(Tag(["flora", "photosynthesis"]))` and `ExactTag(Tag(["flora", "*"])` and `ExactTag(Tag(["fauna", "creature", "*"]))` and `ExactTag(Tag(["ecosystem", "*"]))`.

This pattern is used by the `party-bus` library to enable expressing granular logging via environment variable. Ostensibly you could use it for other stuff too.
