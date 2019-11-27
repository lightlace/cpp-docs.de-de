---
title: Compilerwarnung (Stufe 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: 99dd99eee3c305a53c5ea03235d23a2520768176
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541828"
---
# <a name="compiler-warning-level-4-c4212"></a>Compilerwarnung (Stufe 4) C4212

nicht dem Standard entsprechende Erweiterung: die Funktionsdeklaration hat Ellipsen verwendet.

Der Funktionsprototyp weist eine Variable Anzahl von Argumenten auf. Die Funktionsdefinition ist nicht.

Im folgenden Beispiel wird C4212 generiert:

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```