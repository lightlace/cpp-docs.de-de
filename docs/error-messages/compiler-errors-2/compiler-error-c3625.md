---
title: Compilerfehler C3625 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3625
dev_langs:
- C++
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ebb7a94e807dbd8bbb9e5614f15d03e9b577858
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022594"
---
# <a name="compiler-error-c3625"></a>Compilerfehler C3625

„native_type“: Ein systemeigener Typ kann nicht vom verwalteten oder WinRT-Typ „Typ“ abgeleitet werden.

Eine systemeigene Klasse kann nicht von einer verwalteten oder WinRT-Klasse erben. Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3625 generiert:

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
