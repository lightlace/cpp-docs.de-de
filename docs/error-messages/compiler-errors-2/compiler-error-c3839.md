---
title: Compilerfehler C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: b8382213fbe7cc953dafd9610bfb993ba7837947
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613012"
---
# <a name="compiler-error-c3839"></a>Compilerfehler C3839

Ändern der Ausrichtung in einem verwalteten oder WinRT-Typ nicht möglich

Die Ausrichtung von Variablen in verwalteten oder Windows-Runtime-Typen wird durch die CLR oder Windows-Runtime gesteuert und kann nicht geändert werden, mit [ausrichten](../../cpp/align-cpp.md).

Im folgenden Beispiel wird C3839 generiert:

```
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```