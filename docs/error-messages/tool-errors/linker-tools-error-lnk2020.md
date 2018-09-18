---
title: Linkertoolfehler Lnk2020 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90088d311bac7ee4ce59797d5dcbe148a24963f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034966"
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