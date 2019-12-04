---
title: Compilerfehler C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 0dfe9f88fcdfda1325150d480670777a4d42d896
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758631"
---
# <a name="compiler-error-c2537"></a>Compilerfehler C2537

"Spezifizierer": unzulässige Verknüpfungs Angabe

Mögliche Ursachen:

1. Der Bindungsspezifizierer wird nicht unterstützt. Nur der Bindungsspezifizierer "C" wird unterstützt.

1. Die C-Verknüpfung wird für mehr als eine Funktion in einem Satz überladener Funktionen angegeben. Dieser Vorgang ist nicht zulässig.

Im folgenden Beispiel wird C2537 generiert:

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
