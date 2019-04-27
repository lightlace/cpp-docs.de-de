---
title: Schwerwiegender Fehler C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: f3c9f9bde5da7fb120accbb9a8d72e5715ab9d2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229418"
---
# <a name="fatal-error-c1081"></a>Schwerwiegender Fehler C1081

'Symbol': Dateiname zu lang

Die Länge des ein Pfadname der Datei überschreitet `_MAX_PATH` (als 260 Zeichen STDLIB.h definiert). Kürzen Sie den Namen der Datei.

Wenn Sie mit einem kurzen Dateinamen CL.exe aufrufen, muss der Compiler kann einen vollständigen Pfadnamen generieren. Z. B. `cl -c myfile.cpp` kann dazu führen, dass den Compiler generiert:

```
D:\<very-long-directory-path>\myfile.cpp
```