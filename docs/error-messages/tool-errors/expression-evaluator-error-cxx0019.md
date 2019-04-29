---
title: Ausdrucksauswertungsfehler CXX0019
ms.date: 11/04/2016
f1_keywords:
- CXX0019
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
ms.openlocfilehash: 266e97f28cf0f27cb87e9743399c66aba87c0e8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397106"
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