---
title: Mathematischer Fehler M6111 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95a55ec6b7cdf0b6e4c15bd283dde77c610698fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074824"
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