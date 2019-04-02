---
title: Compilerfehler C2978
ms.date: 11/04/2016
f1_keywords:
- C2978
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
ms.openlocfilehash: cf682bf14246754cca74a43dffc39761ff6125c1
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780300"
---
# <a name="compiler-error-c2978"></a>Compilerfehler C2978

Syntaxfehler: 'Schlüsselwort1' oder 'Schlüsselwort2' wurde erwartet, der Typ 'Schlüsselwort3' wurde gefunden. Nichttypparameter werden für Generics nicht unterstützt.

Eine generische Klasse wurde falsch deklariert. Finden Sie unter [Generika](../../extensions/generics-cpp-component-extensions.md)für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2978 generiert:

```
// C2978.cpp
// compile with: /clr /c
generic <ref class T>   // C2978
// try the following line instead
// generic <typename T>   // OK
ref class Utils {
   static void sort(T elems, size_t size);
};

generic <int>
// try the following line instead
// generic <class T>
ref class Utils2 {
   static void sort(T elems, size_t size);
};
```