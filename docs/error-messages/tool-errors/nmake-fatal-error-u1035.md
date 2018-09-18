---
title: 'NMAKE: Schwerwiegender Fehler U1035 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1035
dev_langs:
- C++
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0383bf4742d637d669070efa5370ebda0c7ab159
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019860"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE: Schwerwiegender Fehler U1035

Syntaxfehler: erwartet ':' oder '=' Trennzeichen

Entweder ein Doppelpunkt (**:**) oder ein Gleichheitszeichen (**=**) wurde erwartet.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Ein Doppelpunkt folgen kein Ziel.

1. Folgen ein Ziel mit einem Buchstaben, einem Doppelpunkt und ohne Leerzeichen (z. B. a:). NMAKE, die sie als eine Laufwerkangabe interpretiert.

1. Ein Doppelpunkt nicht auf eine Rückschlussregel folgen.

1. Eine Makrodefinition wurde nicht durch ein Gleichheitszeichen gefolgt.

1. Ein Zeichen gefolgt von einem umgekehrten Schrägstrich (**\\**), die zum Fortsetzen eines Befehls in eine neue Zeile verwendet wurde.

1. Eine Zeichenfolge angezeigt, die keine NMAKE Syntaxregel folgen.

1. Das Makefile wurde durch ein Textverarbeitungsprogramm formatiert.