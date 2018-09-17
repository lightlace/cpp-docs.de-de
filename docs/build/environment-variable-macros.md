---
title: Makros von Umgebungsvariablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cebb544b1d8fc8489de298bf7512cc612a6dfef2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701167"
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

[Besondere NMAKE-Makros](../build/special-nmake-macros.md)