---
title: Compilerwarnung (Stufe 2) C4099 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d7ffee02e8e5414a0e06cc4ba0da77a50c75f53
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110171"
---
# <a name="compiler-warning-level-2-c4099"></a>Compilerwarnung (Stufe 2) C4099

'Bezeichner': Typ den zuerst mithilfe von "Objekttyp1 ' und jetzt mit"%objecttype2"

Ein Objekt, das als eine Struktur deklariert wird als eine Klasse definiert, oder ein Objekt, das als eine Klasse deklariert wird als Struktur definiert. Der Compiler verwendet den Typ in der Definition.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4099 generiert.

```
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```