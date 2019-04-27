---
title: Schwerwiegender Fehler C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 8fe6b0f3bb1253f72c97f29070ba81cdbdf80508
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166658"
---
# <a name="fatal-error-c1071"></a>Schwerwiegender Fehler C1071

Unerwartetes Dateiende innerhalb eines Kommentars

Der Compiler hat das Ende der Datei erreicht, beim Scannen eines Kommentars.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Kommentar-Abschlusszeichen fehlt (* /).

1. Fehlende neue Zeilenumbruchzeichen nach einem Kommentar in der letzten Zeile in einer Quelldatei.

Im folgende Beispiel wird die C1071 generiert:

```
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```