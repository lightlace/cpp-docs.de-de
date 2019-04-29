---
title: Compilerfehler C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 5ff57050980ddb770ea2fcfa4d0be4f42f5ee834
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391893"
---
# <a name="compiler-error-c3809"></a>Compilerfehler C3809

'class': Ein verwalteter oder WinRT-Typ kann weder über Friends, Funktionen, Klassen noch Schnittstellen verfügen

Friends werden durch verwaltete und Windows-Runtime-Typen nicht unterstützt. Deklarieren Sie zum Beheben dieses Fehlers Friends nicht innerhalb von verwalteten oder Windows-Runtime-Typen.

Im folgenden Beispiel wird C3809 generiert.

```
// C3809a.cpp
// compile with: /clr
ref class A {};

ref class B
{
public:
   friend ref class A;   // C3809
};

int main()
{
}
```