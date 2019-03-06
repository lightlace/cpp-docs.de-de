---
title: Stapelverarbeitungsregeln
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 106db69327bbad112be7efea6970845956e52431
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416669"
---
# <a name="batch-mode-rules"></a>Stapelverarbeitungsregeln

```
{frompath}.fromext{topath}.toext::
   commands
```

Im Batchmodus-Rückschlussregeln geben nur einen Aufruf der Rückschlussregel, wenn diese Rückschlussregel N Befehle durchlaufen. Ohne im Batchmodus-Rückschlussregeln müssten N Befehle aufgerufen werden. N ist die Anzahl von abhängigen Dateien, die die Rückschlussregel auslösen.

Makefiles, die im Batchmodus-Rückschlussregeln enthalten, müssen NMAKE Version 1.62 oder höher verwenden. Um die NMAKE-Version zu überprüfen, führen Sie das _NMAKE_VER-Makro, das zur Verfügung mit NMAKE, Version, 1.62 oder höher. Dieses Makro gibt eine Zeichenfolge mit der Visual C++-Version zurück.

Der Unterschied nur syntaktische standard Rückschlussregel ist, die im Batchmodus Rückschlussregel mit zwei Doppelpunkten (:) beendet wird.

> [!NOTE]
>  Das Tool, das aufgerufen wird, muss mehrere Dateien zu verarbeiten sein. Die im Batchmodus Rückschlussregel muss verwenden `$<` als das Makro mit abhängigen Dateien zugreifen.

Die im Batchmodus-Rückschlussregeln können den Buildprozess beschleunigen. Es ist schneller Dateien an den Compiler im Batch angeben, da der Compilertreiber nur einmal aufgerufen wird. Beispielsweise bietet der C- und C++-Compiler eine bessere Leistung bei der Verarbeitung eines Satzes von Dateien, da es während des Prozesses speicherresident bleiben kann.

Das folgende Beispiel zeigt, wie Sie mit der im Batchmodus-Rückschlussregeln:

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE: erzeugt die folgende Ausgabe ohne im Batchmodus-Rückschlussregeln:

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE: führt zu folgendem Ergebnis mit den im Batchmodus-Rückschlussregeln:

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)
