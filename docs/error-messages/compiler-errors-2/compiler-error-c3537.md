---
title: Compilerfehler C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 50a06180dabfa192292fae7ba1962b6b7455bb89
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024023"
---
# <a name="compiler-error-c3537"></a>Compilerfehler C3537

'Typ': Sie können nicht eine Umwandlung in einen Typ, der "auto" enthält

Eine Variable, die den angegebenen Typ kann nicht umgewandelt werden, da der Typ enthält die `auto` -Schlüsselwort und die standardmäßige [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) Compileroption aktiviert ist.

## <a name="example"></a>Beispiel

Der folgende Code wird C3537 erzeugt, da die Variablen auf einen Typ umgewandelt werden, die enthält die `auto` Schlüsselwort.

```
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../../cpp/auto-keyword.md)