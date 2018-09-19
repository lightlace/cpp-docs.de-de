---
title: 'NMAKE: Schwerwiegender Fehler U1070 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1070
dev_langs:
- C++
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb462e5c3c7e497cde55151bf92c62ffb2afcd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087018"
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