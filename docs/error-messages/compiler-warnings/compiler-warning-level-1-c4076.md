---
title: Compilerwarnung (Stufe 1) C4076 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0a8066b8e79b75f3d5ede37f4e5ad6b61db168
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037878"
---
# <a name="compiler-warning-level-1-c4076"></a>Compilerwarnung (Stufe 1) C4076

> "*Typmodifizierer*": kann nicht verwendet werden, mit dem Typ '*Typename*"

## <a name="remarks"></a>Hinweise

Ein Typmodifizierer kann, ob **signiert** oder **ohne Vorzeichen**, kann nicht mit einem nicht ganzzahligen Datentyp verwendet werden. *Typmodifizierer* wird ignoriert.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4076 generiert; Um dies zu beheben, entfernen Sie die **ohne Vorzeichen** Typmodifizierer:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```