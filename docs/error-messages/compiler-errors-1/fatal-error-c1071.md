---
title: Schwerwiegender Fehler C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 2f39359d55b5564c6379c84f07e942cf3484e011
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747409"
---
# <a name="fatal-error-c1071"></a>Schwerwiegender Fehler C1071

Unerwartetes Dateiende innerhalb eines Kommentars

Der Compiler hat beim Scannen eines Kommentars das Ende der Datei erreicht.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Fehlendes Kommentar Abschluss Zeichen (*/).

1. Fehlendes Zeilen Trennzeichen nach einem Kommentar in der letzten Zeile einer Quelldatei.

Im folgenden Beispiel wird C1071 generiert:

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
