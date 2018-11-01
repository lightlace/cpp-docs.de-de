---
title: Explizite Spezialisierung von Funktionsvorlagen
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: 3d91383f895f1a8be983efe42f685419ca988823
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665178"
---
# <a name="explicit-specialization-of-function-templates"></a>Explizite Spezialisierung von Funktionsvorlagen

Bei einer Funktionsvorlage können Sie ein spezielles Verhalten für einen bestimmten Typ definieren, indem Sie eine explizite Spezialisierung (Überschreibung) der Funktionsvorlage für diesen Typ angeben. Zum Beispiel:

```cpp
template<> void MySwap(double a, double b);
```

Diese Deklaration können Sie eine andere Funktion für definieren **doppelte** Variablen. Ebenso wie nicht auf Vorlagen basierende Funktionen, standardmäßige typkonvertierungen (z. B. Höherstufen einer Variable des Typs **"float"** zu **doppelte**) angewendet werden.

## <a name="example"></a>Beispiel

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[Funktionsvorlagen](../cpp/function-templates.md)