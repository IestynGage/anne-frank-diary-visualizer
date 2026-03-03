

How many letters are they?
* `[a-zA-Z]*, [0-9]* .*194[234]` Regex to find dates returned with 168
* `Je Anne` returned 168.
* `Lieve Kitty` returned with 157.
* `(maandag|dinsdag|woensdag|donderdag|vrijdag|zaterdag|zondag), [12]?[0-9]`
* `(maandag|dinsdag|woensdag|donderdag|vrijdag|zaterdag|zondag)(ochtend|middag|avond)?, [12]?[0-9].*194[234]` 165
* sed 's/\(Maandag\|Dinsdag\|Woensdag\|Donderdag\|Vrijdag\|Zaterdag\|Zondag\)/\n&/g'

```sh
sed -E '/(Maandag|Dinsdag|Woensdag|Donderdag|Vrijdag|Zaterdag|Zondagochtend|Zondag), [12]?[0-9].*194[234]/i\
---\
' diary.txt > diary-formatted.txt
```

```sh
sed -E '/[a-zA-Z]*, [0-9]* .*194[234]/i\
---\
---\
' diary.txt > diary-formatted-2.txt
```