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
ms.openlocfilehash: 9f1e78bd88f35240e90332ef9a9139558051cab5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070126"
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