---
title: Compilerfehler C2955
ms.date: 03/28/2017
f1_keywords:
- C2955
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
ms.openlocfilehash: 8afdeaf43c0c9789753b9165f1e8a8287aaac76d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742872"
---
# <a name="compiler-error-c2955"></a>Compilerfehler C2955

'Bezeichner': Die Verwendung der Klassenvorlage oder des generischen Alias erfordert eine Vorlagen- bzw. eine generische Argumentliste.

Eine Klassenvorlage oder generische Klasse kann ohne Vorlagen- bzw. generische Argumentliste nicht als Bezeichner verwendet werden.

Weitere Informationen finden Sie unter [Klassen Vorlagen](../../cpp/class-templates.md).

Im folgenden Beispiel wird C2955 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

C2955 kann auch bei dem Versuch auftreten, eine abweichende Definition für eine Funktion zu erstellen, die in einer Klassenvorlage deklariert wurde:

```cpp
// C2955_b.cpp
// compile with: /c
template <class T>
class CT {
public:
   void CTFunc();
   void CTFunc2();
};

void CT::CTFunc() {}   // C2955

// OK - this is how to fix it
template <class T>
void CT<T>::CTFunc2() {}
```

C2955 kann auch auftreten, wenn Generics verwendet werden:

```cpp
// C2955_c.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC^ g;   // C2955
   GC <int>^ g;
}
```

## <a name="example"></a>Beispiel

**Visual Studio 2017 und höher:** Der Compiler diagnostiziert fehlende Vorlagen Argumentlisten ordnungsgemäß, wenn die Vorlage in einer Vorlagen Parameterliste angezeigt wird (z. b. als Teil eines Standardvorlagen Arguments oder eines Nichttyp-Vorlagen Parameters). Der folgende Code kompiliert in Visual Studio 2015, aber erzeugt in Visual Studio 2017 einen Fehler.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
