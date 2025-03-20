[< к содержанию](./readme.md) | [в начало >](./about.md)

## git show [хэш]

Команда `git show` отображает объект в простом и человекопонятном виде. Обычно она используется для просмотра информации о метке или коммите.

Git достаточно умён, чтобы понять какой коммит имеется ввиду по нескольким первым символам его хеша, если указанная часть SHA-1 имеет в длину по крайней мере четыре символа и однозначна — то есть в текущем репозитории существует только один объект с таким частичным SHA-1.

Например, предположим, чтобы найти некоторый коммит, вы выполнили команду `git log` и нашли коммит, в которой добавили определённую функциональность:

```
$ git log
commit 734713bc047d87bf7eac9674765ae793478c50d3
Author: Scott Chacon <schacon@gmail.com>
Date:   Fri Jan 2 18:32:33 2009 -0800

    Fix refs handling, add gc auto, update tests

commit d921970aadf03b3cf0e71becdaab3147ba71cdef
Merge: 1c002dd... 35cfb2b...
Author: Scott Chacon <schacon@gmail.com>
Date:   Thu Dec 11 15:08:43 2008 -0800

    Merge commit 'phedders/rdocs'

commit 1c002dd4b536e7479fe34593e72e6c6c1819e53b
Author: Scott Chacon <schacon@gmail.com>
Date:   Thu Dec 11 14:58:32 2008 -0800

    Add some blame and merge stuff
```

Предположим, что в нашем примере это коммит `1c002dd…​.`. Если вы хотите выполнить для него `git show`, то следующие команды эквиваленты (предполагается, что сокращения однозначны):

```
$ git show 1c002dd4b536e7479fe34593e72e6c6c1819e53b
$ git show 1c002dd4b536e7479f
$ git show 1c002d
```