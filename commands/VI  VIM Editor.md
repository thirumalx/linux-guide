# VI / VIM Editor

### Open a File

```bash
vi filename
```

### Go to the Last Line

Press:

```text
Esc
G
```

### Common VI Commands

| Command | Function            |
| ------- | ------------------- |
| `i`     | Insert mode         |
| `Esc`   | Exit insert mode    |
| `G`     | Go to last line     |
| `gg`    | Go to first line    |
| `:w`    | Save                |
| `:q`    | Quit                |
| `:wq`   | Save and quit       |
| `:q!`   | Quit without saving |
| `/text` | Search for text     |

---

## Replace text
Press `Esc` button and enter the following command

```bash
:%s/old_string/new_string/g

Example

:%s/was/were/g
```