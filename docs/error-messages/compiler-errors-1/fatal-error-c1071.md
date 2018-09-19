---
title: Schwerwiegender Fehler C1071 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4487de60148e1da7668bc44c996c5dfb955a9d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033003"
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