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
ms.openlocfilehash: 928b0a78c09773e334c1a291877b74304dab66ec
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198477"
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