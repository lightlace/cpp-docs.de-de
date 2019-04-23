---
title: Compilerfehler C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: 3465c3275783a625c172b711e9c41789b6f36713
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777457"
---
# <a name="compiler-error-c2959"></a>Compilerfehler C2959

eine generische Klasse oder Funktion kann nicht Mitglied einer Vorlage sein.

Weitere Informationen finden Sie unter [Windows-Laufzeit und verwaltete Vorlagen](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) und [Generika](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2959 generiert.

```
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```