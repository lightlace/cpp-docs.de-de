---
title: Compilerfehler C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: 6aff2e5c96e3c79fc748d8a95779d6a08647ab03
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739622"
---
# <a name="compiler-error-c2785"></a>Compilerfehler C2785

' Deklaration1 ' und ' Deklaration2 ' haben unterschiedliche Rückgabe Typen.

Der Rückgabetyp der Funktions Vorlagen Spezialisierung unterscheidet sich vom Rückgabetyp der primären Funktions Vorlage.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie alle Spezialisierungs Funktionen der Funktions Vorlage auf Konsistenz.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2785 generiert:

```cpp
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```
