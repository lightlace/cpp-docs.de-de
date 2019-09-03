---
title: '##undef-Anweisung (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 1a69bc568579e7da7c7e3816cb67c8153b8f1a27
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220220"
---
# <a name="undef-directive-cc"></a>#undef-Direktive (C++C/)

Entfernt einen Namen, der zuvor mit `#define` erstellt wurde (hebt die Definierung auf).

## <a name="syntax"></a>Syntax

> **#undef** *Bezeichner*

## <a name="remarks"></a>Hinweise

Die **#undef** -Direktive entfernt die aktuelleDefinition des Bezeichners. Folglich werden nachfolgende vorkommen des Bezeichners vom Präprozessor ignoriert. Um eine Makro Definition mithilfe **#undef**zu entfernen, sollten Sie nur den Makro Bezeichner und keine Parameterliste angeben.

Sie können die **#undef** -Direktive auch auf einen Bezeichner anwenden, der keine vorherige Definition hat. Dadurch wird sichergestellt, dass der Bezeichner nicht definiert wird. Makro Ersetzung wird nicht innerhalb von **#undef** -Anweisungen ausgeführt.

Die **#undef** -Anweisung ist in der Regel `#define` mit einer-Direktive gekoppelt, um einen Bereich in einem Quell Programm zu erstellen, in dem ein Bezeichner eine besondere Bedeutung hat. Beispielsweise kann eine bestimmte Funktion des Quellprogramms Manifestkonstanten verwenden, um umgebungsspezifische Werte zu definieren, die sich nicht auf das übrige Programm auswirken. Die **#undef** -Direktive funktioniert auch `#if` mit der-Direktive, um die bedingte Kompilierung des Quell Programms zu steuern. Weitere Informationen finden Sie in [den Anweisungen #if, #elif, #else und #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

Im folgenden Beispiel entfernt die **#undef** -Direktive Definitionen einer symbolischen Konstante und eines Makros. Beachten Sie, dass nur der Bezeichner des Makros angegeben wird.

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft-spezifisch**

Makros können in der Befehlszeile mit der `/U` -Option nicht definiert werden, gefolgt von den zu undefinierten Makronamen. Die Auswirkung der Ausgabe dieses Befehls entspricht einer Sequenz von `#undef` *Makronamen* Anweisungen am Anfang der Datei.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
