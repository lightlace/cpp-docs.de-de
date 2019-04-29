---
title: Linkertoolfehler LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 7290a90dfd92d84c4632e7f9dd38d36eccd4ac27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386329"
---
# <a name="linker-tools-error-lnk2020"></a>Linkertoolfehler LNK2020

nicht aufgelöstes Token "Token"

Ähnlich wie ein nicht definierter externen Fehler, außer dass der Verweis über Metadaten ist. In den Metadaten die alle Funktionen und Daten definiert werden.

Um zu beheben:

- Definieren Sie die fehlende Funktion oder Daten, oder

- Enthalten Sie die Objektdatei oder eine Bibliothek, die in dem die fehlende Funktion oder die Daten bereits definiert ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK2020 generiert.

```
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

LNK2020 tritt auch auf, wenn Sie erstellen Sie eine Variable eines Typs verwalteten Vorlage, aber auch nicht den Typ instanziiert.

Im folgende Beispiel wird die LNK2020 generiert.

```
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