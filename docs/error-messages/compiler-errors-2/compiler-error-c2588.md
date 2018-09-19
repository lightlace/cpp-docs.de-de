---
title: Compilerfehler C2588 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d656dbde06d6052fd10611675f2cff8818cdb6e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108571"
---
# <a name="compiler-error-c2588"></a>Compilerfehler C2588

":: ~ Identifier': Unzulässiger globaler-Destruktor

Der Destruktor wird für andere als eine Klasse, Struktur oder Union definiert. Dies ist nicht zulässig.

Dieser Fehler kann verursacht werden, durch eine fehlende Klasse, Struktur oder union Namen auf der linken Seite des Bereichsauflösungsoperators (`::`) Operator.

Im folgende Beispiel wird die C2588 generiert:

```
// C2588.cpp
~F();   // C2588
```