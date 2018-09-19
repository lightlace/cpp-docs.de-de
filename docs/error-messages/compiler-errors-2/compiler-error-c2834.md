---
title: Compilerfehler C2834 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b94e1a3fba9bc3589af020340651b4546347cf1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089345"
---
# <a name="compiler-error-c2834"></a>Compilerfehler C2834

'Operator Operator' muss Global angegeben werden.

Die `new` und `delete` Operatoren sind befinden, in dem Sie sich auf die Klasse gebunden. Bereichsauflösung kann nicht verwendet werden, zum Auswählen einer Version von `new` oder `delete` von einer anderen Klasse. Um mehrere Formen eines implementieren die `new` oder `delete` -Operator, erstellen Sie eine Version des Operators mit zusätzlichen formalen Parametern.