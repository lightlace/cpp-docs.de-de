---
title: Mathematischer Fehler M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 44f406881d64d13e23ca2c0911ee278c864a2c11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510785"
---
# <a name="math-error-m6111"></a>Mathematischer Fehler M6111

Stack Unterlauf

Eine Gleitkommaoperation führte ein Stapelunterlauf dem 8087/287/387-Coprozessor oder im Emulator.

Dieser Fehler wird häufig durch einen Aufruf verursacht eine `long double` -Funktion, die keinen Wert zurückgibt. Die folgenden generiert z. B. diesen Fehler bei der Kompilierung und Ausführung:

```
long double ld() {};
main ()
{
  ld();
}
```

Das Programm mit Exitcode 139 wird beendet.