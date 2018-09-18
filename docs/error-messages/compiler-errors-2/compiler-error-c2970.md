---
title: Compilerfehler C2970 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 978d843243cdceb294bc83dbac7a2725a7ec9eed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070729"
---
# <a name="compiler-error-c2970"></a>Compilerfehler C2970

'Klasse': Vorlagenparameter 'Param': 'Arg': ein Ausdruck, der Objekte mit interner Verknüpfung kann nicht als Nichttyp Argument verwendet werden

Sie können nicht den Namen oder die Adresse einer statischen Variablen als Vorlagenargument verwenden. Die Vorlagenklasse erwartet, dass einen const-Wert, der zur Kompilierzeit ausgewertet werden kann.

Im folgende Beispiel wird die C2970 generiert:

```
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```