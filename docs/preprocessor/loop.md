---
title: Loop
ms.date: 10/18/2018
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: a1640881d98073381a941478f4b78177a95698d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411330"
---
# <a name="loop"></a>Loop

Steuert, wie Schleifencode durch die automatische Parallelisierung berücksichtigt werden soll und/oder schließt eine Schleife von der Berücksichtigung durch die automatische Vektorisierung aus.

## <a name="syntax"></a>Syntax

```
#pragma loop( hint_parallel(n) )
#pragma loop( no_vector )
#pragma loop( ivdep )
```

### <a name="parameters"></a>Parameter

*hint_parallel(n)*<br/>
Weist den Compiler an, die über diese Schleife parallelisiert werden soll *n* Threads, in denen *n* ist ein positives Ganzzahlliteral oder 0 (null). Wenn *n* NULL ist, wird die maximale Anzahl von Threads zur Laufzeit verwendet. Dies ist ein Hinweis für den Compiler, kein Befehl, und es gibt keine Garantie dafür, dass die Schleife parallelisiert wird. Wenn die Schleife Datenabhängigkeiten oder strukturelle Probleme aufweist, z. B. in der Schleife in einen über den Schleifentext hinaus verwendeten Skalar gespeichert wird, dann wird die Schleife nicht parallelisiert.

Der Compiler ignoriert diese Option aus, es sei denn, die [/Qpar](../build/reference/qpar-auto-parallelizer.md) -Compilerschalter wird angegeben.

*no_vector*<br/>
Standardmäßig ist die automatische Vektorisierung aktiviert und versucht, alle Schleifen zu vektorisieren, für die dies als nützlich bewertet wird. Geben Sie dieses Pragma an, um die automatische Vektorisierung für die darauf folgende Schleife zu deaktivieren.

*ivdep*<br/>
Weist den Compiler darauf hin, Vektorabhängigkeiten für diese Schleife zu ignorieren. Verwenden Sie diese in Verbindung mit *Hint_parallel*.

## <a name="remarks"></a>Hinweise

Verwenden der **Schleife** Pragma, platzieren Sie es direkt vor – nicht in – eine Schleifendefinition. Das Pragma gilt für den Gültigkeitsbereich der Schleife, die darauf folgt. Sie können mehrere Pragmas in beliebiger Reihenfolge auf eine Schleife anwenden, aber Sie müssen jedes in einer separaten Pragmaanweisung angeben.

## <a name="see-also"></a>Siehe auch

[Automatische Parallelisierung und automatische Vektorisierung](../parallel/auto-parallelization-and-auto-vectorization.md)<br/>
[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)