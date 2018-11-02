---
title: Compilerwarnung (Stufe 4) C4459
ms.date: 11/04/2016
f1_keywords:
- C4459
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
ms.openlocfilehash: 0cbab7c7cca1fc88bb99210262be45c56b6be7a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585067"
---
# <a name="compiler-warning-level-4-c4459"></a>Compilerwarnung (Stufe 4) C4459

> Deklaration von "*Bezeichner*" Blendet globale Deklaration

Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet die Deklaration der identischen *Bezeichner* im globalen Bereich. Diese Warnung teilt Ihnen mitteilen, dass Verweise auf *Bezeichner* in diesem Bereich zu beheben, auf die lokal deklarierten Version nicht die globale Version, die möglicherweise nicht Ihrer Absicht. Im Allgemeinen wird empfohlen, dass Sie die Verwendung der globalen Variablen als einem angemessenen Entwicklungsverfahren minimieren. Um der Verunreinigung des globalen Namespace zu minimieren, empfehlen wir die Verwendung eines benannten Namespaces für globale Variablen.

Diese Warnung ist neu in Visual Studio 2015, Visual c++-Compilerversion 18.00 Uhr. Um Warnungen zu dieser Version des Compilers oder später während der Migration von Code zu unterdrücken, verwenden die [/Wv:18](../../build/reference/compiler-option-warning-level.md) -Compileroption.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4459 generiert:

```cpp
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() {
    int global_or_local; // warning C4459
    global_or_local = 2;
}
```

Eine Möglichkeit zum Beheben dieses Problems besteht darin erstellen Sie einen Namespace für Ihre globale jedoch nicht die Verwendung einer `using` Direktive, um diesen Namespace in den Gültigkeitsbereich, bringen, damit alle Verweise, die eindeutig verwenden müssen qualifizierte Namen:

```cpp
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() {
    int global_or_local; // OK
    global_or_local = 2;
    globals::global_or_local = 3;
}
```
