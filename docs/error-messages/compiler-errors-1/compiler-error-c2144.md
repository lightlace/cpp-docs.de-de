---
title: Compilerfehler C2144 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2144
dev_langs:
- C++
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60a6b0a6019ab6ddf1a403d2cbd4f6ef96b2a865
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171147"
---
# <a name="compiler-error-c2144"></a>Compilerfehler C2144

> Syntaxfehler: "*Typ*"sollte vorangestellt werden"*token*"

Der Compiler erwartet *token* und *Typ* stattdessen.

Dieser Fehler kann durch eine fehlende schließende Klammer gefunden, schließende Klammern oder durch Semikolons verursacht werden.

C2144 kann auch auftreten, wenn Sie versuchen, erstellen Sie ein Makro aus einem CLR-Schlüsselwort, das ein Leerzeichen enthält.

C2144 möglicherweise auch angezeigt, wenn Sie versuchen, die Weiterleitung eingeben. Finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md) für Weitere Informationen.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel wird C2144 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Im folgenden Beispiel wird C2144 generiert und zeigt eine Möglichkeit, sie diesen Fehler beheben:

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