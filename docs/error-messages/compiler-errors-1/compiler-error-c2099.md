---
title: Compilerfehler C2099
ms.date: 11/04/2016
f1_keywords:
- C2099
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
ms.openlocfilehash: 9c83b4a50cb9cf5c5b1992f0f64e2eeb013b48e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575759"
---
# <a name="compiler-error-c2099"></a>Compilerfehler C2099

Initialisierung ist keine Konstante

Dieser Fehler wird nur vom C-Compiler ausgegeben und tritt nur für nicht automatische Variablen auf.  Der Compiler initialisiert beim Programmstart nicht automatische Variablen und die Werte, mit denen sie initialisiert werden, müssen konstant sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2099 generiert.

```
// C2099.c
int j;
int *p;
j = *p;   // C2099 *p is not a constant
```

## <a name="example"></a>Beispiel

C2099 kann auch auftreten, da der Compiler keine Konstantenfaltung für einen Ausdruck unter **/fp:strict** ausführen kann, da die Umgebungseinstellung für die Gleitkommagenauigkeit (weitere Informationen finden Sie unter [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) ) möglicherweise zwischen Kompilierungs- und Laufzeit abweichen.

Wenn bei der Konstantenfaltung ein Fehler auftritt, ruft der Compiler die dynamische Initialisierung auf, die in C nicht zulässig ist.

Kompilieren Sie das Modul als CPP-Datei, oder vereinfachen Sie den Ausdruck, um diesen Fehler zu beheben.

Weitere Informationen finden Sie unter [/fp (Specify Floating-Point Behavior)](../../build/reference/fp-specify-floating-point-behavior.md).

Im folgenden Beispiel wird C2099 generiert.

```
// C2099_2.c
// compile with: /fp:strict /c
float X = 2.0 - 1.0;   // C2099
float X2 = 1.0;   // OK
```