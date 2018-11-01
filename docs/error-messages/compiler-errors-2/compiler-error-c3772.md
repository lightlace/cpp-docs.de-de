---
title: Compilerfehler C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 9a72cb9ee5d1d839f6ca5d113c25795f83dab811
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595675"
---
# <a name="compiler-error-c3772"></a>Compilerfehler C3772

"Name": Ungültige Friend-Vorlagendeklaration.

Es ist unzulässig, einen "Friend" einer Spezialisierung einer Klassenvorlage zu deklarieren. Sie können keine explizite oder partielle Spezialisierung einer Klassenvorlage deklarieren und in derselben Anweisung einen "Friend" dieser Spezialisierung deklarieren. Die *Name* -Platzhalter identifiziert die ungültige Deklaration.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Sie sollten keinen "Friend" der Spezialisierung einer Klassenvorlage deklarieren.

- Deklarieren Sie einen "Friend" der Klassenvorlage oder einen "Friend" einer bestimmten partiellen oder expliziten Spezialisierung, sofern dies für Ihre Anwendung geeignet ist.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel tritt ein Fehler auf, da ein "Friend" einer partiellen Spezialisierung einer Klassenvorlage deklariert wird.

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>Siehe auch

[Vorlagen](../../cpp/templates-cpp.md)<br/>
[Vorlagenspezialisierung](../../cpp/template-specialization-cpp.md)
