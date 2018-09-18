---
title: Schwerwiegender Fehler C1081 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b34f2f19a0bb8770ea9292fef120c415c0fb255a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060528"
---
# <a name="fatal-error-c1081"></a>Schwerwiegender Fehler C1081

'Symbol': Dateiname zu lang

Die Länge des ein Pfadname der Datei überschreitet `_MAX_PATH` (als 260 Zeichen STDLIB.h definiert). Kürzen Sie den Namen der Datei.

Wenn Sie mit einem kurzen Dateinamen CL.exe aufrufen, muss der Compiler kann einen vollständigen Pfadnamen generieren. Z. B. `cl -c myfile.cpp` kann dazu führen, dass den Compiler generiert:

```
D:\<very-long-directory-path>\myfile.cpp
```