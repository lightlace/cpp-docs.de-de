---
title: Compilerwarnung (Stufe 3) C4638
ms.date: 08/27/2018
f1_keywords:
- C4638
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
ms.openlocfilehash: 1bdd7541e16f5c02756678ae78a777094b5fe588
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401657"
---
# <a name="compiler-warning-level-3-c4638"></a>Compilerwarnung (Stufe 3) C4638

> XML-dokumentkommentarziel: Verweis auf unbekanntes Symbol '*Symbol*"

## <a name="remarks"></a>Hinweise

Der Compiler konnte ein Symbol nicht auflösen (*Symbol*). Das Symbol muss in der Kompilierung gültig sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4638 generiert:

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```