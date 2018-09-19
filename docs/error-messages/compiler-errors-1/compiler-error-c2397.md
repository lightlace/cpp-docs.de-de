---
title: Compilerfehler C2397 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- C2397
dev_langs:
- C++
ms.assetid: b418cf5a-d50d-4a6c-98a7-994ae35046d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3e76384ca2509663398fd7abd7badfd4057e8c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115098"
---
# <a name="compiler-error-c2397"></a>Compilerfehler C2397

Konvertierung von 'type_1' zu 'type_2' erfordert eine einschränkende Konvertierung

Eine implizite einschränkende Konvertierung wurde gefunden, wenn Sie einheitliche Initialisierung verwenden.

Die Programmiersprache C ermöglicht implizite einschränkende Konvertierungen in Zuweisungen und Initialisierung und C++-aufgespielte, auch wenn unerwartete einschränkende eine Ursache für viele Fehler in Code ist. Um den Code sicherer zu gestalten, erfordert der C++-standard eine diagnosemeldung aus, tritt eine einschränkende Konvertierung in eine Initialisierungsliste. In Visual C++ ist die Diagnose Compilerfehler C2397 beim Beginn unterstützte Syntax einheitliche Initialisierung in Visual Studio 2015. Der Compiler generiert [Compilerwarnung (Stufe 1) C4838](../../error-messages/compiler-warnings/compiler-warning-level-1-c4838.md) bei Verwendung der Liste aus oder aggregatinitialisierungssyntax von Visual Studio 2013 unterstützt werden.

Eine einschränkende Konvertierung kann kein Problem sein, wenn Sie wissen, dass die Bandbreite der konvertierten Werte in der Ziel-eingepasst werden kann. In diesem Fall wissen Sie mehr als der Compiler übernimmt. Wenn Sie eine einschränkende Konvertierung bewusst machen, stellen Sie Ihre Absichten explizit über eine statische Umwandlung. Andernfalls gibt diese Fehlermeldung an fast immer, dass Sie einen Fehler in Ihrem Code verfügen. Sie können ihn beheben, indem Sie sicherstellen, dass die Objekte, die Sie initialisieren aufweisen, die groß genug, um die Eingaben zu verarbeiten sind.

Im folgenden Beispiel wird die C2397 generiert und zeigt eine Möglichkeit, das Problem zu beheben:

```
// C2397.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C2397.cpp
#include <vector>

struct S1 {
    int m1;
    double m2, m3;
};

void function_C2397(double d1) {
    char c1 { 127 };          // OK
    char c2 { 513 };          // error C2397

    std::vector<S1> vS1;
    vS1.push_back({ d1, 2, 3 }); // error C2397

    // Possible fix if you know d1 always fits in an int
    vS1.push_back({ static_cast<int>(d1), 2, 3 });
}
```