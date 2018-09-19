---
title: Compilerfehler C3894 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 373da78257ee0f5ce7307ab521cccb0297933240
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080089"
---
# <a name="compiler-error-c3894"></a>Compilerfehler C3894

'Var': l-Wert-Verwendung der statischen Initonly-Datenmembers ist nur zulässig, in den Konstruktor der Klasse der Klasse "Klasse"

Statische [Initonly](../../dotnet/initonly-cpp-cli.md) Datenmember können nur als l-Werte zum Zeitpunkt der Deklaration oder in einem statischen Konstruktor verwendet werden.

Instanz (nicht statisch) Initonly-Datenmember können nur als l-Werte zum Zeitpunkt der Deklaration oder in den Instanzkonstruktoren der (nicht statisch) verwendet werden.

Im folgende Beispiel wird die C3894 generiert:

```
// C3894.cpp
// compile with: /clr
ref struct Y1 {
   initonly static int data_var = 0;

public:
   // class constructor
   static Y1() {
      data_var = 99;   // OK
      System::Console::WriteLine("in static constructor");
   }

   // not the class constructor
   Y1(int i) {
      data_var = i;   // C3894
   }

   static void Test() {}

};

int main() {
   Y1::data_var = 88;   // C3894
   int i = Y1::data_var;
   Y1 ^ MyY1 = gcnew Y1(99);
   Y1::Test();
}
```