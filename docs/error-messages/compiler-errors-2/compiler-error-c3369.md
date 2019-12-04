---
title: Compilerfehler C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: ee936f4921369b1d59d81b51dcb3e81c69be083c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755602"
---
# <a name="compiler-error-c3369"></a>Compilerfehler C3369

"Modulname": idl_module ist bereits definiert

Der [idl_module](../../windows/idl-module.md) -Anwendungskontext, in dem Sie die DLL definieren, kann pro Programm nur einmal vorkommen.

Im folgenden Beispiel wird C3369 generiert:

```cpp
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```
