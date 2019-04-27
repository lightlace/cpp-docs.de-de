---
title: Compilerfehler C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: 3a0fd9c49a71f6f53d1a109378e3a6894bb68723
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175422"
---
# <a name="compiler-error-c2146"></a>Compilerfehler C2146

Syntaxfehler: Fehlendes "token" vor Bezeichner 'Identifier'

Der Compiler erwartet `token` und `identifier` stattdessen.  Mögliche Ursachen:

1. Fehler bei Rechtschreib- oder Groß-/Kleinschreibung.

1. Fehlender Typspezifizierer in der Deklaration des Bezeichners.

Dieser Fehler kann durch einen Tippfehler verursacht werden. Fehler [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) in der Regel vor dem dieser Fehler.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2146 generiert.

```
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

## <a name="example"></a>Beispiel

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde, generiert werden: fehlende `typename` Schlüsselwort.

Im folgende Beispiel wird in Visual Studio .NET 2002 kompiliert, aber in Visual Studio .NET 2003 fehl:

```
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

## <a name="example"></a>Beispiel

Außerdem sehen Sie diesen Fehler infolge einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde: explizite spezialisierungen werden nicht mehr die Vorlageparameter aus der primären Vorlage gefunden.

Die Verwendung von `T` aus der primären Vorlage ist in der expliziten Spezialisierung nicht zulässig. Ersetzen Sie alle Instanzen des Vorlagenparameters in der Spezialisierung für Code in Visual Studio .NET 2003 und Visual Studio .NET Version von Visual C++ gültig ist mit dem explizit spezialisierte Typ.

Im folgende Beispiel kompiliert in Visual Studio .NET aber in Visual Studio .NET 2003 fehl:

```
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```