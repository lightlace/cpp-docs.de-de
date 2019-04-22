---
title: Compilerfehler C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 48b378eb734c5830bedbf417d99d34955e2e6d0f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023268"
---
# <a name="compiler-error-c3551"></a>Compilerfehler C3551

"spät angegebener Rückgabetyp erwertet"

Wenn Sie das `auto` -Schlüsselwort als Platzhalter für den Rückgabetyp einer Funktion verwenden, müssen Sie einen spät angegebenen Rückgabetyp angeben. Im folgenden Beispiel ist der spät angegebene Rückgabetyp der Funktion `myFunction` ein Zeiger auf ein Array mit vier Elementen vom Typ `int`.

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>Siehe auch

[auto](../../cpp/auto-cpp.md)