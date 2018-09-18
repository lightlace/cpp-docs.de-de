---
title: Compilerfehler C3062 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95f2e58cada0b1b825fb0f065b461db6350de9fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067167"
---
# <a name="compiler-error-c3062"></a>Compilerfehler C3062

"Enum": Enumerator ist ein Wert erforderlich, da der zugrunde liegenden Typ 'Typ'

Sie können einen zugrunde liegenden Typ für eine Enumeration angeben. Allerdings erfordern einige Typen Zuweisen von Werten für jeden Enumerator.

Weitere Informationen über Enumerationen finden Sie unter [Enumerationsklasse](../../windows/enum-class-cpp-component-extensions.md).

Im folgende Beispiel wird die C3062 generiert:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```