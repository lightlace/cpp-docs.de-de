---
title: Befehlszeilenwarnung D9027 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105ebbf62027ac3d9377c513c4f7c59e261b983d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112524"
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