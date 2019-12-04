---
title: Compilerfehler C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: a2e4ca81194968fb50a5442cab3d229a25b8be1b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754679"
---
# <a name="compiler-error-c2633"></a>Compilerfehler C2633

' Identifier ': ' Inline ' ist die einzige zulässige Speicher Klasse für Konstruktoren.

Ein Konstruktor wird als eine andere Speicher Klasse als Inline deklariert.

Im folgenden Beispiel wird C2633 generiert:

```cpp
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
