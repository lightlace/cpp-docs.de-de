---
title: optimize-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 6d7b99b7a72c133d56a209cf42fa9ef670a4a7f9
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220513"
---
# <a name="optimize-pragma"></a>optimize-Pragma

Gibt Optimierungen für Funktionsweise an.

## <a name="syntax"></a>Syntax

> **#pragma optimieren ("** [ *Optimization-List* ] **",** { **on** | **Off** } **)**

## <a name="remarks"></a>Hinweise

Das **Optimierungs** -Pragma muss außerhalb einer Funktion angezeigt werden. Dies tritt bei der ersten Funktion in Kraft, die definiert wird, nachdem das Pragma angezeigt wird. Mit den **on** -und **Off** -Argumenten werden die in der *Optimierungs Liste* angegebenen Optionen aktiviert oder deaktiviert.

Die *Optimierungs Liste* kann NULL oder mehr der in der folgenden Tabelle aufgeführten Parameter sein.

### <a name="parameters-of-the-optimize-pragma"></a>Parameter des optimize-Pragmas

| Parameter | Typ der Optimierung |
|--------------------|--------------------------|
| **g** | Aktivieren globale Optimierungen. |
| **s** oder **t** | Geben kurze oder schnelle Sequenzen von Computercode an. |
| **y** | Generieren Framezeiger im Programmstapel. |

Diese Parameter sind die gleichen Buchstaben, die mit den [/O](../build/reference/o-options-optimize-code.md) -Compileroptionen verwendet werden. Beispielsweise ist folgendes Pragma mit der `/Os`-Compileroption identisch:

```cpp
#pragma optimize( "s", on )
```

Die Verwendung des **Optimierungs** -Pragmas mit der leeren Zeichenfolge ( **""** ) ist eine besondere Form der Direktive:

Wenn Sie den **Off** -Parameter verwenden, werden alle Optimierungen, **g**, **s**, **t**und **y**, deaktiviert.

Wenn Sie den **on** -Parameter verwenden, werden die Optimierungen auf die Optimierungen zurückgesetzt, die Sie mithilfe der [/O](../build/reference/o-options-optimize-code.md) -Compileroption angegeben haben.

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
