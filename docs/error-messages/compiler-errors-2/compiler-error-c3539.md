---
title: Compilerfehler C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: be1051859ebbcbdc22a9b71f8c5adba2e75c4e92
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025175"
---
# <a name="compiler-error-c3539"></a>Compilerfehler C3539

'Typ': ein Vorlagenargument handelt es sich nicht um ein Typ, der "auto" enthält

Der Argumenttyp für die angegebene Vorlage darf keine Verwendung von enthalten die `auto` Schlüsselwort.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Geben Sie nicht die Template-Argument, mit der `auto` Schlüsselwort.

## <a name="example"></a>Beispiel

Im folgende Beispiel ergibt C3539.

```
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)