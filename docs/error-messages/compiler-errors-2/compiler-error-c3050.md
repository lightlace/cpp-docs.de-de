---
title: Compilerfehler C3050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3050
dev_langs:
- C++
helpviewer_keywords:
- C3050
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a4c5220cbfc897f2952d366d9ce09bfb8d85dc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243658"
---
# <a name="compiler-error-c3050"></a>Compilerfehler C3050
'Typ1': Eine Verweisklasse kann nicht von 'Typ1' erben.  
  
 `System::ValueType` kann keine Basisklasse für einen Verweistyp sein.  
  
 Im folgenden Beispiel wird C3050 generiert:  
  
```  
// C3050.cpp  
// compile with: /clr /LD  
ref struct X : System::ValueType {};   // C3050  
ref struct Y {};   // OK  
```