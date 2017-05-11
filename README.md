# Emoticon_Regex :simple_smile:

The regexes matches emoticons and kaomojis that can be found in [`emoticons.json`](./emoticons.json).

## Emoticon

###Human readable

```python
pixelart = {
	"yinyang": r"69|\(\.\\°\)",
	"buttock": r"\([_ ][Y¤)()][_ ]\)",
	"breast": r"\( [o\.] (?:\)\(|Y) [o\.] \)",
	"penis": r"(?:\(_\)_\)|[c83])=+[D3]",
	"vulva": r"{\('\)}",
	"rose": r"@}[->',]+",
	"snail": r"_@_/|i@_"
}

components = {
	"hat": r"(?:\*?[03<>]|\(\)|3>)",
	"eyes": r"(?:[¦|:;=38BEXxz@%+]|\(:\))",
	"nose": r"[-'o^~]",
	"mouth": r"[\)\(\|\]\[}{>3DdQPpOoXxSs@€*$#/\\°~]",
	"pixelart": r"<(?:/|\\)?3|&\[ \]|\[]==\[]|\(___\(--#|>°\)+><|{yinyang}|{buttock}|{breast}|{penis}|{vulva}|{snail}|{rose}".format(**pixelart)
}

emoticon = r"{hat}?{eyes}'?{nose}?{mouth}|{mouth}{nose}?'?{eyes}{hat}?|{pixelart}".format(**components)
```
### Expanded

```python
emoticon = r"(?:\*?[03<>]|\(\)|3>)?(?:[¦|:;=38BEXxz@%+]|\(:\))'?[-'o^~]?[\)\(\|\]\[}{>3DdQPpOoXxSs@€*$#/\\°~]|[\)\(\|\]\[}{>3DdQPpOoXxSs@€*$#/\\°~][-'o^~]?'?(?:[¦|:;=38BEXxz@%+]|\(:\))(?:\*?[03<>]|\(\)|3>)?|<(?:/|\\)?3|&\[ \]|\[]==\[]|\(___\(--#|>°\)+><|69|\(\.\\°\)|\([_ ][Y¤)()][_ ]\)|\( [o\.] (?:\)\(|Y) [o\.] \)|(?:\(_\)_\)|[c83])=+[D3]|{\('\)}|_@_/|i@_|@}[->',]+"
```

## Kaomoji

### Human readable

```python
components = {
	"eye": r"\[?[éèn-u=µ\-`´;\"@vQTPç0ÔOo.ôUX'x*¤+$^°><~¬]\]?",
	"mouth": r"([_,0Oµou.-3AwpmQqWvV\-]|[_/]+)",
	"sweat": r"[\"']",
	"cheek": r"[)(|?]",
	"arm": r"[\\/)(o]",
	"head": r"[o°]"
}
kaomoji = r"{arm}?{cheek}?{eye} ?{mouth}? ?{eye}{sweat}?{cheek}?{arm}?|{arm}{head}{arm}".format(**components)
```

### Expanded

```python
kaomoji = r"[\\/)(o]?[)(|?]?\[?[éèn-u=µ\-`´;\"@vQTPç0ÔOo.ôUX\'x*¤+$^°><~¬]\]? ?([_,0Oµou.-3AwpmQqWvV\-]|[_/]+)? ?\[?[éèn-u=µ\-`´;\"@vQTPç0ÔOo.ôUX\'x*¤+$^°><~¬]\]?[\"\']?[)(|?]?[\\/)(o]?|[\\/)(o][o°][\\/)(o]"
```

## To go further

These repos are about emoticons too. Check them out :
* [wooorm/emoticon](https://github.com/wooorm/emoticon)
* [OhLookCake/EmoticonSentiment](https://github.com/OhLookCake/EmoticonSentiment)
* [telabotanica/binette.js](https://github.com/telabotanica/binette.js)

A method to detect kaomojis :
Steven Bedrick, Russell Beckley, Brian Roark, and Richard Sproat. 2012. [Robust Kaomoji Detection in Twitter](http://aclanthology.info/papers/robust-kaomoji-detection-in-twitter). In Proceedings of the Second Workshop on Language in Social Media (LSM '12). Association for Computational Linguistics, Stroudsburg, PA, USA, 56-64.