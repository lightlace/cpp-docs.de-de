---
title: Compilerfehler C2946 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91af822dd21adf9125162ed997e71ed548c863ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027686"
---
# <a name="compiler-error-c2946"></a>Compilerfehler C2946

Explizite Instanziierung: "Klasse" ist keine Spezialisierung einer Vorlagenklasse

Nicht auf Vorlagen basierende Klassen können nicht explizit instanziiert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2946 generiert.

```
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```