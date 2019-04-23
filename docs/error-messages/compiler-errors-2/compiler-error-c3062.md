---
title: Compilerfehler C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 6f4157db4a2a1b1864446a082deddc73df2e2fe9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778708"
---
# <a name="compiler-error-c3062"></a>Compilerfehler C3062

"Enum": Enumerator ist ein Wert erforderlich, da der zugrunde liegenden Typ 'Typ'

Sie können einen zugrunde liegenden Typ für eine Enumeration angeben. Allerdings erfordern einige Typen Zuweisen von Werten für jeden Enumerator.

Weitere Informationen über Enumerationen finden Sie unter [Enumerationsklasse](../../extensions/enum-class-cpp-component-extensions.md).

Im folgende Beispiel wird die C3062 generiert:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```