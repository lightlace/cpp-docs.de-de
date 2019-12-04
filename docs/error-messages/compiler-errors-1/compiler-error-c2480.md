---
title: Compilerfehler C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 3e495a8019405a558511637467133877dae1183e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743522"
---
# <a name="compiler-error-c2480"></a>Compilerfehler C2480

"Bezeichner": "Thread" ist nur für Datenelemente mit statischem Wertebereich gültig.

Das `thread`-Attribut kann nicht mit einer automatischen Variablen, einem nicht statischen Datenmember, einem Funktionsparameter oder in Funktions Deklarationen oder-Definitionen verwendet werden.

Verwenden Sie das `thread`-Attribut nur für globale Variablen, statische Datenmember und lokale statische Variablen.

Im folgenden Beispiel wird C2480 generiert:

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
