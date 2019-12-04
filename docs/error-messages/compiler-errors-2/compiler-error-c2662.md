---
title: Compilerfehler C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: b2fa2643898fed510aa7cf0f483b538ebb33b033
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760451"
---
# <a name="compiler-error-c2662"></a>Compilerfehler C2662

"Funktion": der this-Zeiger kann nicht von "Typ1" in "Typ2" konvertiert werden.

Der Compiler konnte den `this` Zeiger nicht von `type1` in `type2`konvertieren.

Dieser Fehler kann verursacht werden, wenn eine nicht-`const` Member-Funktion für ein `const`-Objekt aufgerufen wird.  Mögliche Lösungen:

- Entfernen Sie die `const` aus der Objekt Deklaration.

- Fügen Sie `const` der Member-Funktion hinzu.

Im folgenden Beispiel wird C2662 generiert:

```cpp
// C2662.cpp
class C {
public:
   void func1();
   void func2() const{}
} const c;

int main() {
   c.func1();   // C2662
   c.func2();   // OK
}
```

Beim Kompilieren mit **/CLR**können Sie keine Funktion für einen `const` oder `volatile` qualifizierten verwalteten Typ aufzurufen. Sie können keine konstantenmember-Funktion einer verwalteten Klasse deklarieren, sodass Sie keine Methoden für verwaltete verwaltete Objekte abrufen können.

```cpp
// C2662_b.cpp
// compile with: /c /clr
ref struct M {
   property M^ Type {
      M^ get() { return this; }
   }

   void operator=(const M %m) {
      M ^ prop = m.Type;   // C2662
   }
};

ref struct N {
   property N^ Type {
      N^ get() { return this; }
   }

   void operator=(N % n) {
      N ^ prop = n.Type;   // OK
   }
};
```

Im folgenden Beispiel wird C2662 generiert:

```cpp
// C2662_c.cpp
// compile with: /c
// C2662 expected
typedef int ISXVD;
typedef unsigned char BYTE;

class LXBASE {
protected:
    BYTE *m_rgb;
};

class LXISXVD:LXBASE {
public:
   // Delete the following line to resolve.
   ISXVD *PMin() { return (ISXVD *)m_rgb; }

   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK
};

void F(const LXISXVD *plxisxvd, int iDim) {
   ISXVD isxvd;
   // Delete the following line to resolve.
   isxvd = plxisxvd->PMin()[iDim];

   isxvd = plxisxvd->PMin2()[iDim];
}
```
