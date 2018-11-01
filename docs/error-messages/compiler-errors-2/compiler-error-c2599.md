---
title: Compilerfehler C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: 872c3a66d4738c1a69990dffdbbc59cee9e90002
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544637"
---
# <a name="compiler-error-c2599"></a>Compilerfehler C2599

"Enum": Die Vorwärtsdeklaration Enum-Typs ist nicht zulässig.

Der Compiler unterstützt nicht mehr die Vorwärtsdeklaration einer verwalteten Enumeration.

Vorwärtsdeklaration einer Enum-Typs ist nicht zulässig, unter [/Za](../../build/reference/za-ze-disable-language-extensions.md).

Im folgende Beispiel wird der Fehler C2599 generiert:

```
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```