# Task 2 - Context-Free Grammar

## 1. Sequence of letters from A to Z

- Terminals (T): {A, B, ..., Z}
- Nonterminals (N): {LETTER, SEQUENCE}
- Productions (P):

```plaintext
S -> A | B | ... | Z | S S
A -> 'a' | ... | 'z'
B -> 'a' | ... | 'z'
...
Z -> 'a' | ... | 'z'
```

```plaintext
SEQUENCE -> LETTER SEQUENCE | LETTER
LETTER -> A | B | ... | Z
Start Symbol (S): SEQUENCE
```

```markdown
            SEQUENCE
          /       \
      LETTER      SEQUENCE
        |         /       \
        A     LETTER     SEQUENCE
                  |       /      \
                  B   LETTER   SEQUENCE
                        |        |
                        C      LETTER
                                |
                                D
```

## 2. Strings consisting of terminals 'break', 'tab', 'newline'

- Terminals (T): {break, tab, newline}
- Nonterminals (N): {COMMAND, COMMAND_SEQUENCE}
- Productions (P):

```plaintext
S -> 'tab' S | 'break' S | 'newline' S | ε
```

```plaintext
COMMAND_SEQUENCE -> COMMAND COMMAND_SEQUENCE | COMMAND
COMMAND -> break | tab | newline
Start Symbol (S): COMMAND_SEQUENCE
```

```markdown
    COMMAND_SEQUENCE
          /           \
      COMMAND   COMMAND_SEQUENCE
        |        /              \
      tab     COMMAND         COMMAND_SEQUENCE
                |           /              \
            newline     COMMAND        COMMAND_SEQUENCE
                          |              |
                        tab          COMMAND
                                        |
                                      break
```

## 3. Rows that consist of letters or numbers starting with a number

- Terminals (T): {0, 1, ..., 9, A, B, ..., Z}
- Nonterminals (N): {NUMBER, ALPHANUM, ALPHANUM_SEQUENCE}
- Productions (P):

```plaintext
S -> N L
N -> '0' | '1' | ... | '9'
L -> 'a' | ... | 'z' | '0' | '1' | ... | '9' | L L
```

```plaintext
ALPHANUM_SEQUENCE -> NUMBER ALPHANUM_SEQUENCE | ALPHANUM
ALPHANUM -> NUMBER | LETTER
NUMBER -> 0 | 1 | ... | 9
LETTER -> A | B | ... | Z
Start Symbol (S): ALPHANUM_SEQUENCE
```

```plaintext
        ALPHANUM_SEQUENCE
            /        \
       NUMBER     ALPHANUM_SEQUENCE
          |           /        \
          5     ALPHANUM   ALPHANUM_SEQUENCE
                    |              |
                LETTER        ALPHANUM
                    |              |
                    A           LETTER
                                  |
                                  B
```
