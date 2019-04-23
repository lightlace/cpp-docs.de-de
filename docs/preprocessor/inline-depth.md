---
title: inline_depth
ms.date: 11/04/2016
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
ms.openlocfilehash: 18d772c8a9f6218ed3afaa385f214445bd0fe8e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039019"
---
# <a name="inlinedepth"></a>inline_depth
Gibt an die Inlineheuristik suchen, Tiefe, so, dass keine Funktion inline gestellt werden, wenn es auf einer Ebene (im Aufrufdiagramm) größer ist *n*.

## <a name="syntax"></a>Syntax

```
#pragma inline_depth( [n] )
```

## <a name="remarks"></a>Hinweise

Dieses Pragma steuert das inlining von Funktionen, die markiert [Inline](../cpp/inline-functions-cpp.md) und ["__inline"](../cpp/inline-functions-cpp.md) oder Inlining automatisch unter die `/Ob2` Option.

*n* kann ein Wert zwischen 0 und 255, wobei 255 unendliche Tiefe im Aufrufdiagramm, und NULL die Inlineerweiterung sein.  Wenn *n* nicht angegeben ist, wird der Standardwert (254) verwendet.

Die **Inline_depth** Pragma steuert die Anzahl der Male, die eine Reihe von Funktionsaufrufen erweitert werden kann. Wenn die Inlinetiefe z. B. vier ist und A B aufruft und B dann C, werden alle drei Aufrufe inline erweitert. Wenn jedoch die nächste Inlineerweiterung zwei ist, werden nur A und B erweitert, und C bleibt als Funktionsaufruf bestehen.

Um dieses Pragma verwenden zu können, müssen Sie festlegen der `/Ob` Compileroption auf 1 oder 2. Die bei der Verwendung dieses Pragma festgelegte Tiefe ist beim ersten Funktionsaufruf nach dem Pragma wirksam.

Die Inlinetiefe kann während der Erweiterung verringert, aber nicht erhöht werden. Wenn die inlinetiefe sechs ist und während der Erweiterung der Präprozessor erkennt eine **Inline_depth** bleibt von Pragma mit einem Wert von 8 – die Tiefe sechs.

Die **Inline_depth** Pragma hat keine Auswirkungen auf Funktionen, die mit markierten `__forceinline`.

> [!NOTE]
> Rekursive Funktionen können inline in einer maximalen Tiefe von 16 Aufrufen ersetzt werden.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_recursion](../preprocessor/inline-recursion.md)