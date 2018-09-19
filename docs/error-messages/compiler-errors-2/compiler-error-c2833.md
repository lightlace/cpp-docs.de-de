---
title: Compilerfehler C2833 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2833
dev_langs:
- C++
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53360c1eaf81ad407589fbdb125d9e6fe017708e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070170"
---
# <a name="compiler-error-c2833"></a>Compilerfehler C2833

'Operator Operator' ist kein bekannter Operator oder Typ

Das Wort `operator` muss ein Operator, der Sie überschreiben möchten oder ein Typ, die Sie konvertieren möchten folgen.

Eine Liste der Operatoren, die Sie in einem verwalteten Typ definieren können, finden Sie unter [benutzerdefinierte Operatoren](../../dotnet/user-defined-operators-cpp-cli.md).

Im folgende Beispiel wird die C2833 generiert:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```