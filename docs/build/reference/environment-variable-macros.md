---
title: Makros von Umgebungsvariablen
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: 7f7f8a05545658142001b75ac78975251185a033
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825297"
---
# <a name="environment-variable-macros"></a>Makros von Umgebungsvariablen

NMAKE: erbt Makrodefinitionen für Umgebungsvariablen, die vor dem Start der Sitzung vorhanden sind. Wenn eine Variable in der Betriebssystem-Umgebung festgelegt wurde, ist es als eines NMAKE-Makros zur Verfügung. Die geerbten Namen werden in Großbuchstaben konvertiert. Vererbung erfolgt vor dem Präprozessorlauf. Verwenden Sie die e /-Option, um die dazu führen, dass Makros von Umgebungsvariablen mit dem gleichen Namen in das Makefile überschrieben geerbt.

Makros von Umgebungsvariablen können in der Sitzung neu definiert werden, und die entsprechende Umgebungsvariable geändert. Sie können auch Umgebungsvariablen mit dem Befehl SET ändern. Mit dem SET-Befehl so ändern Sie eine Umgebungsvariable in einer Sitzung wird das entsprechende Makro, nicht jedoch geändert.

Zum Beispiel:

```
PATH=$(PATH);\nonesuch

all:
    echo %PATH%
```

In diesem Beispiel ändern `PATH` ändert sich die entsprechende Umgebungsvariable `PATH`; Es fügt `\nonesuch` zu Ihrem Pfad.

Wenn eine Variable als Zeichenfolge, die in einem Makefile syntaktisch falsch wäre definiert ist, wird kein Makro erstellt, und keine Warnung generiert wird. Wenn der Wert einer Variablen ein Dollarzeichen ($) enthält, wird es von NMAKE als Anfang eines Makroaufrufs interpretiert. Mit dem Makro kann unerwartetes Verhalten verursachen.

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
