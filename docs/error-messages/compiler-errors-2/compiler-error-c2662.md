---
title: Compilerfehler C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: fefd523ca3b9a3406afc307150322f9d431aa730
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515244"
---
# <a name="compiler-error-c2662"></a>Compilerfehler C2662

'Funktion': "this"-Zeiger von 'type1' in 'Typ2' kann nicht konvertiert werden.

Der Compiler konnte nicht konvertiert werden. die `this` Zeiger von `type1` zu `type2`.

Dieser Fehler kann verursacht werden, durch den Aufruf einer nicht -`const` Member-Funktion auf einem `const` Objekt.  Mögliche Lösungen:

- Entfernen Sie die `const` aus der Objektdeklaration.

- Hinzufügen `const` auf die Member-Funktion.

Im folgende Beispiel wird die C2662 generiert:

```
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

Beim Kompilieren mit **"/ CLR"**, Sie können für eine Funktion aufrufen einer `const` oder `volatile` gekennzeichneten verwalteten Typ. Eine const-Memberfunktion einer verwalteten Klasse kann nicht deklariert werden, sodass Sie Methoden für const-verwaltete Objekte aufrufen, können nicht.

```
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

Im folgende Beispiel wird die C2662 generiert:

```
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