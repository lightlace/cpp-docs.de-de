---
title: Compilerfehler C2008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a00c2a55d7176beae88f7e5db3045722568bd293
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051242"
---
# <a name="compiler-error-c2008"></a>Compilerfehler C2008

"Zeichen": unerwartetes Zeichen in Makrodefinition

Das Zeichen, die unmittelbar nach der Makroname wird angezeigt. Um den Fehler zu beheben, muss ein Leerzeichen nach dem Makronamen vorhanden sein.

Im folgende Beispiel wird die C2008 generiert:

```
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Mögliche Lösung:

```
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```