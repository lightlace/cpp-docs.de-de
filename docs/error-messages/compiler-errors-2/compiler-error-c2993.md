---
title: Compilerfehler C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 5aa0d27b2d469f53ec521f587172398b7d4c2d1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761230"
---
# <a name="compiler-error-c2993"></a>Compilerfehler C2993

"Identifier": Ungültiger Typ für den Nichttyp-Vorlagen Parameter "Parameter".

Sie können keine Vorlage mit einem Struktur-oder Union-Argument deklarieren. Verwenden Sie Zeiger, um Strukturen und Unions als Vorlagen Parameter zu übergeben.

Im folgenden Beispiel wird C2993 generiert:

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Dieser Fehler wird auch aufgrund von compilerübereinstimmungs-Aufgaben generiert, die in Visual Studio .NET 2003 ausgeführt wurden: untypvorlagen Parameter für Gleit Komma Werte sind nicht mehr zulässig. Der C++ Standard lässt keine nicht-typvorlagen Parameter für Gleit Komma Werte zu.

Wenn es sich um eine Funktions Vorlage handelt, verwenden Sie ein Funktions Argument, um den nicht-typvorlagen Parameter für Gleit Komma Zeichen zu übergeben (dieser Code ist in Visual Studio .NET 2003 und Visual Studio .net C++-Versionen von Visual Studio gültig). Wenn es sich um eine Klassen Vorlage handelt, gibt es keine einfache Problem Umgehung.

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
