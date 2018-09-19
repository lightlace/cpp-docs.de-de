---
title: Kommentare in einem Makefile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bff732a0e9becc9b6c829c70a1bc6701e6031bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723949"
---
# <a name="comments-in-a-makefile"></a>Kommentare in einem Makefile

Stellen Sie einen Kommentar mit einem Nummernzeichen voran (##). NMAKE: ignoriert Text aus dem Nummernzeichen auf das nächste neue Zeilenumbruchzeichen. Beispiele:

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

Um ein literalen Nummernzeichen anzugeben, fügen sie davor ein Caretzeichen (**^**) wie folgt:

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>Siehe auch

[Inhalt eines Makefiles](../build/contents-of-a-makefile.md)