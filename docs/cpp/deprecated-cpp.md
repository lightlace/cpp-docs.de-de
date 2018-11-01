---
title: deprecated (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: 34f9c10cd898b0359463d5933141822576fa4a11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485851"
---
# <a name="deprecated-c"></a>deprecated (C++)

In diesem Thema geht es um die Microsoft-spezifischen veraltet "declspec"-Deklaration. Informationen zu den C ++ 14 `[[deprecated]]` -Attribut und Anleitungen zur Verwendung dieses Attributs im Vergleich zu den Microsoft-spezifische "declspec" "oder" Pragma, finden Sie unter [Standard C++-Attribute](attributes.md).

Mit den unten aufgeführten Ausnahmen die **veraltet** Deklaration bietet die gleiche Funktionalität wie die [veraltet](../preprocessor/deprecated-c-cpp.md) Pragma:

- Die **veraltet** Deklaration können Sie bestimmte Arten von funktionsüberladungen als veraltet angeben, wohingegen das Pragma auf alle überladenen Arten eines Funktionsnamens angewendet wird.

- Die **veraltet** Deklaration ermöglicht die Angabe eine Nachricht, die zum Zeitpunkt der Kompilierung angezeigt werden. Der Text der Meldung kann von einem Makro stammen.

- Makros können nur markiert werden, als veraltet mit der **veraltet** Pragma.

Findet der Compiler die Verwendung von einen veralteten Bezeichner oder Standard [ `[[deprecated]]` ](attributes.md) -Attribut, eine [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) Warnung wird ausgelöst.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Funktionen als veraltet gekennzeichnet werden und wie eine Meldung angegeben wird, die bei Verwendung einer veralteten Funktion zur Kompilierzeit angezeigt wird.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Klassen als veraltet gekennzeichnet werden und wie eine Meldung angegeben wird, die bei Verwendung einer veralteten Klasse zur Kompilierzeit angezeigt wird.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)