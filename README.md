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

## Acknowledgements
- Big shoutout to [75lb](https://github.com/75lb) for creating the Javascript library this project is modeled after: https://github.com/75lb/ansi-escape-sequences
