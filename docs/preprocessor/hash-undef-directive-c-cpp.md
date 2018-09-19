---
title: '#Undef-Anweisung (C/C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c98c6559e04f0e89fa4c3501f30cd88d449de306
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42543144"
---
# <a name="undef-directive-cc"></a>#undef-Anweisung (C/C++)
Entfernt einen Namen, der zuvor mit `#define` erstellt wurde (hebt die Definierung auf).  
  
## <a name="syntax"></a>Syntax  
  
```  
#undef   
identifier  
```  
  
## <a name="remarks"></a>Hinweise 

Die **#undef** -Anweisung entfernt die aktuelle Definition der *Bezeichner*. Folglich weiteren Vorkommen *Bezeichner* werden vom Präprozessor ignoriert. So entfernen Sie eine Makrodefinition mithilfe **#undef**, geben Sie nur mit dem Makro *Bezeichner* ; Geben Sie keine Parameterliste.  
  
Sie können auch anwenden, die **#undef** -Direktive ein Bezeichner, der keine vorherige Definition hat. Dadurch wird sichergestellt, dass der Bezeichner nicht definiert wird. Makroersetzung wird nicht ausgeführt, in **#undef** Anweisungen.  
  
Die **#undef** Richtlinie wird in der Regel zusammen mit einem `#define` Direktive, um einen Bereich in einem Quellprogramm zu erstellen, in denen ein Bezeichner eine besondere Bedeutung hat. Beispielsweise kann eine bestimmte Funktion des Quellprogramms Manifestkonstanten verwenden, um umgebungsspezifische Werte zu definieren, die sich nicht auf das übrige Programm auswirken. Die **#undef** Richtlinie funktioniert auch mit der `#if` Direktive für bedingte Kompilierung des Quellprogramms steuern. Finden Sie unter [#if-, #elif-, #else- und #endif-Direktiven](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) für Weitere Informationen.  
  
Im folgenden Beispiel die **#undef** -Anweisung entfernt die Definitionen einer symbolischen Konstante und eines Makros. Beachten Sie, dass nur der Bezeichner des Makros angegeben wird.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
**Microsoft-spezifisch**  
  
Makros können in der Befehlszeile mit werden die `/U` Option, gefolgt von den gewünschten Makronamen, nicht definiert werden. Die Auswirkungen dieses Befehls entspricht in eine Sequenz von `#undef` *Makronamen* -Anweisungen am Anfang der Datei.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)