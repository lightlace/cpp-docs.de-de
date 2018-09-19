---
title: Compilerfehler C3868 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3868
dev_langs:
- C++
helpviewer_keywords:
- C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f16427bd29e9b72ef169603649535a5c94df9fcb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098876"
---
# <a name="compiler-error-c3868"></a>Compilerfehler C3868

"Type": Einschränkungen für den generischen Parameter 'Parameter' unterscheiden sich von denen die Deklaration

Mehrere Deklarationen müssen dieselben generischen Einschränkungen verfügen.  Weitere Informationen finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3868 generiert.

```
// C3868.cpp
// compile with: /clr /c
interface struct I1;

generic <typename T> ref struct MyStruct;
generic <typename U> where U : I1 ref struct MyStruct;   // C3868

// OK
generic <typename T> ref struct MyStruct2;
generic <typename U> ref struct MyStruct2;

generic <typename T> where T : I1 ref struct MyStruct3;
generic <typename U> where U : I1 ref struct MyStruct3;
```