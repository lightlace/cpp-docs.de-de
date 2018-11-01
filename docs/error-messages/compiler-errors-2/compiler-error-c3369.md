---
title: Compilerfehler C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0cd27da4b73732513afe0bd33a2d7312e6ddbe97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618958"
---
# <a name="compiler-error-c3369"></a>Compilerfehler C3369

"Modulname": idl_module ist bereits definiert

Der [idl_module](../../windows/idl-module.md) -Anwendungskontext, in dem Sie die DLL definieren, kann pro Programm nur einmal vorkommen.

Im folgenden Beispiel wird C3369 generiert:

```
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```