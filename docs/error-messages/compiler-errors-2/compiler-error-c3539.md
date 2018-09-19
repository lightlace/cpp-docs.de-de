---
title: Compilerfehler C3539 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b2f78b69e00290dcc283e3fc340d25a4a071776
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091880"
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