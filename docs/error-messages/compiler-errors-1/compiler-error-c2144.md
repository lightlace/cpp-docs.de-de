---
title: Compilerfehler C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: f6472fc70ee4a86bed1422941e758127009f14cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483329"
---
# <a name="compiler-error-c2144"></a>Compilerfehler C2144

> Syntaxfehler: "*Typ*"sollte auf folgen"*token*"

Der Compiler erwartet *token* und *Typ* stattdessen.

Dieser Fehler kann durch eine fehlende schließende geschweifte Klammer, Rechte Klammer und Semikolon verursacht werden.

C2144 kann auch auftreten, wenn Sie versuchen, ein Makro aus einem CLR-Schlüsselwort zu erstellen, die ein Leerzeichen enthält.

Sie können auch C2144 angezeigt, wenn Sie versuchen, die Weiterleitung eingeben. Finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md) für Weitere Informationen.

## <a name="examples"></a>Beispiele

Im folgende Beispiel wird die C2144 generiert, und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Im folgende Beispiel wird die C2144 generiert, und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```