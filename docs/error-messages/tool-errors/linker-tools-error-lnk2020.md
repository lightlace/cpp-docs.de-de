---
title: Linkertoolfehler LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 9c6be2548e277af08f1069a70b26cd761db835bc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988764"
---
# <a name="linker-tools-error-lnk2020"></a>Linkertoolfehler LNK2020

nicht aufgelöstes Token "Token"

Ähnlich wie ein nicht definierter externer Fehler, mit dem Unterschied, dass der Verweis über Metadaten erfolgt. In den Metadaten müssen alle Funktionen und Daten definiert werden.

Behebung:

- Definieren Sie die fehlenden Funktionen oder Daten, oder

- Fügen Sie die Objektdatei oder-Bibliothek ein, in der die fehlenden Funktionen oder Daten bereits definiert sind.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolfehler LNK2020 generiert.

```cpp
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

## <a name="example"></a>Beispiel

Linkertoolfehler LNK2020 tritt auch auf, wenn Sie eine Variable eines verwalteten Vorlagen Typs erstellen, aber nicht auch den Typ instanziieren.

Im folgenden Beispiel wird Linkertoolfehler LNK2020 generiert.

```cpp
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```
