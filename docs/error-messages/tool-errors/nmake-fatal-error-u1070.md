---
title: 'NMAKE: Schwerwiegender Fehler U1070'
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 35bea47f6626dfe283a537d3d96340921c37f3f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367238"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE: Schwerwiegender Fehler U1070

Schleife in Makrodefinition "Makroname"

Die angegebene Makrodefinition enthalten ein Makro, deren Definition über das angegebene Makro enthalten. Zirkuläre Makrodefinitionen sind ungültig.

## <a name="example"></a>Beispiel

Die folgenden Makrodefinitionen

```
ONE=$(TWO)
TWO=$(ONE)
```

Führen Sie den folgenden Fehler:

```
cycle in macro definition 'TWO'
```