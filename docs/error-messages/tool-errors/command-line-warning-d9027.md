---
title: Befehlszeilenwarnung D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214115"
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