---
title: Compilerfehler C2248 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2248
dev_langs:
- C++
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e3a2f5eb51fe2b3d773a2eeb1881c8f1adb8dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085913"
---
# <a name="compiler-error-c2248"></a>Compilerfehler C2248

"*Member*": kann nicht zugegriffen werden "*Access_level*"Element deklariert in Klasse"*Klasse*"

Member einer abgeleiteten Klasse können nicht zugegriffen werden `private` Member einer Basisklasse. Kann nicht auf `private` oder `protected` Mitglieder von Klasseninstanzen.

## <a name="example"></a>Beispiel

Das folgende Beispiel generiert C2248 generiert, wenn der privaten oder geschützten Member einer Klasse von außerhalb der Klasse zugegriffen werden. Um dieses Problem zu beheben, greifen Sie Sie diese Elemente direkt außerhalb der Klasse nicht zu. Verwenden Sie öffentliche Memberdaten und Memberfunktionen, um mit der Klasse zu interagieren.

```cpp
// C2248_access.cpp
// compile with: cl /EHsc /W4 C2248_access.cpp
#include <stdio.h>

class X {
public:
    int  m_publicMember;
    void setPrivateMember( int i ) {
        m_privateMember = i;
        printf_s("\n%d", m_privateMember);
    }
protected:
    int  m_protectedMember;

private:
    int  m_privateMember;
} x;

int main() {
    x.m_publicMember = 4;
    printf_s("\n%d", x.m_publicMember);
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected
    x.m_privateMember = 3;   // C2248  m_privMemb is private
    x.setPrivateMember(0);   // OK uses public access function
}
```

Ein weiteres Problem auf Übereinstimmung mit Standards, das C2248 verfügbar macht, ist die Verwendung von Friend-Vorlagen und Spezialisierung. Um dieses Problem zu beheben, deklarieren Sie Friend Vorlagenfunktionen mit einer leeren Vorlage Parameter Liste <> oder bestimmte Vorlagenparameter.

```cpp
// C2248_template.cpp
// compile with: cl /EHsc /W4 C2248_template.cpp
template<class T>
void f(T t) {
    t.i;   // C2248
}

struct S {
private:
    int i;

public:
    S() {}
    friend void f(S);   // refer to the non-template function void f(S)
    // To fix, comment out the previous line and
    // uncomment the following line.
    // friend void f<S>(S);
};

int main() {
    S s;
    f<S>(s);
}
```

Ein weiteres Problem auf Übereinstimmung mit Standards, das C2248 verfügbar macht, ist beim Deklarieren von Friend einer Klasse, und wenn die Klasse nicht für die Friend-Deklaration im Gültigkeitsbereich der Klasse angezeigt wird. Um dieses Problem zu beheben, gewähren Sie Friendship-Klasse der einschließenden Klasse.

```cpp
// C2248_enclose.cpp
// compile with: cl /W4 /c C2248_enclose.cpp
class T {
    class S {
        class E {};
    };
    friend class S::E;   // C2248
};

class A {
    class S {
        class E {};
        friend class A;  // grant friendship to enclosing class
    };
    friend class S::E;   // OK
};
```