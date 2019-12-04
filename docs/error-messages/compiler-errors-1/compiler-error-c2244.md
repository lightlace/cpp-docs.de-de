---
title: Compilerfehler C2244
ms.date: 11/04/2016
f1_keywords:
- C2244
helpviewer_keywords:
- C2244
ms.assetid: d9911c12-ceb5-4f93-ac47-b44a485215c2
ms.openlocfilehash: 97ff469c6f3f766bd1b5412133003bae2acaddfc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759476"
---
# <a name="compiler-error-c2244"></a>Compilerfehler C2244

"Bezeichner": die Funktionsdefinition kann nicht mit einer vorhandenen Deklaration abgeglichen werden.

Vor einem Funktions Aufruf, der keine Klammer enthielt, wurde eine ungewöhnliche Verwendung des unären +-Operators verwendet.

Dieser Fehler tritt nur in C++ -Projekten auf.

Im folgenden Beispiel wird C2244 generiert:

```cpp
// C2244.cpp
int func(char) {
   return 0;
}

int func(int) {
   return 0;
}

int main() {
   +func;   // C2244
}
```

C2244 kann auch auftreten, wenn eine falsche Funktions Signatur für eine Member-Funktion einer Klassen Vorlage verwendet wird.

```cpp
// C2244b.cpp
// compile with: /c
template<class T>
class XYZ {
   void func(T t);
};

template<class T>
void XYZ<T>::func(int i) {}   // C2244 wrong function signature
// try the following line instead
// void XYZ<T>::func(T t) {}
```

C2244 kann auch auftreten, wenn eine falsche Funktions Signatur für eine Element Funktions Vorlage verwendet wird.

```cpp
// C2244c.cpp
// compile with: /c
class ABC {
   template<class T>
   void func(int i, T t);
};

template<class T>
void ABC::func(int i) {}   // C2244 wrong signature
// try the following line instead
// void ABC::func(int i, T t) {}
```

Eine Funktions Vorlage kann nicht teilweise spezialisiert werden.

```cpp
// C2244d.cpp
template<class T, class U>
class QRS {
   void func(T t, U u);
};

template<class T>
void QRS<T,int>::func(T t, int u) {}   // C2244
```
