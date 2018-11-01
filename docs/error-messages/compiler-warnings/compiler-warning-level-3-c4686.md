---
title: Compilerwarnung (Stufe 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 5e23e6aa69fe8a59e3dfd22af7e33780c223cdd3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584517"
---
# <a name="compiler-warning-level-3-c4686"></a>Compilerwarnung (Stufe 3) C4686

> "*einen benutzerdefinierten Typ*": mögliche verhaltensänderung, Änderung in der UDT gibt zurück Aufrufkonvention

## <a name="remarks"></a>Hinweise

Eine Spezialisierung einer Klassenvorlage wurde nicht definiert ist, bevor er in einem Rückgabetyp verwendet wurde. Alle Elemente, die die Klasse instanziiert wird C4686; aufgelöst werden deklarieren eine Instanz oder das Zugreifen auf einen Member (C\<Int >:: nichts) sind auch Optionen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Beispiel

Verwenden Sie stattdessen Folgendes:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```