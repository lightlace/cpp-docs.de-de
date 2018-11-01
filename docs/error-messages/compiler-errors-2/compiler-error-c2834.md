---
title: Compilerfehler C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: fb4a0e6f3f6ec227b978ae0b7d3864b2134de986
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677603"
---
# <a name="compiler-error-c2834"></a>Compilerfehler C2834

'Operator Operator' muss Global angegeben werden.

Die `new` und `delete` Operatoren sind befinden, in dem Sie sich auf die Klasse gebunden. Bereichsauflösung kann nicht verwendet werden, zum Auswählen einer Version von `new` oder `delete` von einer anderen Klasse. Um mehrere Formen eines implementieren die `new` oder `delete` -Operator, erstellen Sie eine Version des Operators mit zusätzlichen formalen Parametern.