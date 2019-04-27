---
title: Compilerfehler C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 0bd9193d6e305a4b6c6851ef2524a68ecc056816
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208983"
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