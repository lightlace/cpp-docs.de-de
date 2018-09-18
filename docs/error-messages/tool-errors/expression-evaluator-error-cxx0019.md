---
title: Ausdrucksauswertungsfehler CXX0019 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0019
dev_langs:
- C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fba76b75c640917b3b99cd41500d682cb1b32f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031807"
---
# <a name="expression-evaluator-error-cxx0019"></a>Ausdrucksauswertungsfehler CXX0019

Ungültige Typumwandlung

Die C++-ausdrucksauswertung kann die Typumwandlung laut nicht ausführen.

Dieser Fehler ist mit CAN0019 identisch.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Der angegebene Typ ist unbekannt.

1. Es wurden zu viele Ebenen von Zeigertypen. Z. B. die Typumwandlung

    ```
    (char **)h_message
    ```

     kann nicht von der C++-ausdrucksauswertung ausgewertet werden.