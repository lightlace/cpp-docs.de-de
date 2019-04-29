---
title: Compilerfehler C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: f53312fa9225270ef79d50d2ad351adce790d6fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300532"
---
# <a name="compiler-error-c3367"></a>Compilerfehler C3367

'static_member_function': Eine statische Funktion kann nicht zum Erstellen eines ungebundenen Delegaten verwendet werden.

Wenn Sie einen ungebundenen Delegaten aufrufen, müssen Sie eine Instanz eines Objekts übergeben. Da eine statische Memberfunktion über den Klassennamen aufgerufen wird, können Sie nur einen ungebundenen Delegaten mit einer Instanzmemberfunktion instanziieren.

Weitere Informationen zu nicht gebundene Delegate, finden Sie unter [Vorgehensweise: Definieren und Verwenden von Delegaten (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3367 generiert:

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```