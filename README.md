# ansi-escape-sequences-unison
A small library serving ANSI escape codes and sequences for use in the terminal

## Functionality

### Text styling
The main interface for text styling is the `format` function:
```
format : [Style] -> Text -> Text
```

For example, let's say we had a string defined like this:
```
testString = "unstyled, " ++ (format [Style.italic, Style.bgRed, Style.rgb (1, 2, 3)] "styled") ++ ", and unstyled again"
```

If we printed that to the terminal, we'd get this (result provided via a screenshot, to preserve styling):
![Screenshot](https://i.imgur.com/RMAkel7.png)

### Cursor positioning and visibility
The `cursor` namespace contains the following functions for controlling the cursor:
```
  1.  back               (Nat -> Text)
  2.  down               (Nat -> Text)
  3.  forward            (Nat -> Text)
  4.  hide               (Text)
  5.  horizontalAbsolute (Nat -> Text)
  6.  nextLine           (Nat -> Text)
  7.  position           (Nat -> Nat -> Text)
  8.  previousLine       (Nat -> Text)
  9.  show               (Text)
  10. up                 (Nat -> Text)
```

For example, let's say we had a `run`nable function like so:
```
demo = '(printLine ("line" ++ back 3 ++ "ak" ++ forward 1 ++ "side"))
```
When we run it, we can expect it to print "line", go back 3 characters, overwrite the characters there with "ak", skip forward 1 character, then finish with "side":
```
.> run demo
lakeside
```

## Acknowledgements
- Big shoutout to [75lb](https://github.com/75lb) for creating the Javascript library this project is modeled after: https://github.com/75lb/ansi-escape-sequences
