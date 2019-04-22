---
title: Compilerfehler C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: be1051859ebbcbdc22a9b71f8c5adba2e75c4e92
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
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