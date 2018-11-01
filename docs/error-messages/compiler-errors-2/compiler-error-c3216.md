---
title: Compilerfehler C3216
ms.date: 11/04/2016
f1_keywords:
- C3216
helpviewer_keywords:
- C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
ms.openlocfilehash: 80435c38ff4130938c996b1144aa71300f96eca1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474905"
---
# <a name="compiler-error-c3216"></a>Compilerfehler C3216

Die Einschränkung muss ein generischer Parameter sein, nicht 'Typ'.

Eine Einschränkung wurde nicht ordnungsgemäß formatiert.

Im folgenden Beispiel wird C3216 generiert:

```
// C3216.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where F : A   // C3216
// Try the following line instead:
// where T : A    // C3216
ref class C {};
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```
// C3216b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```