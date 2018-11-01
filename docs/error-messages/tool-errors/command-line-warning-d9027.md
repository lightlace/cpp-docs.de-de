---
title: Befehlszeilenwarnung D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482601"
---
# <a name="command-line-warning-d9027"></a>Befehlszeilenwarnung D9027

Quelldatei "\<Dateiname >" ignoriert

CL.exe ignoriert die Eingabequelldatei.

Diese Warnung kann durch ein Leerzeichen zwischen der/Fo-Option und der Name für die Ausgabedatei in einer Befehlszeile mit der Option/c verursacht werden. Zum Beispiel:

```
cl /c /Fo output.obj input.c
```

Da ein Leerzeichen zwischen/FO und `output.obj`, dauert der CL.exe `output.obj` als den Namen der Eingabedatei. Um das Problem zu beheben, entfernen Sie den Speicherplatz:

```
cl /c /Fooutput.obj input.c
```