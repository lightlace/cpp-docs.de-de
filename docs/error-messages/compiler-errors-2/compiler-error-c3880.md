---
title: Compilerfehler C3880 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3880
dev_langs:
- C++
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc36f3b5fb9571a707e4ffe4e75182e984e407
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3880"></a>Compilerfehler C3880
"Var": nicht mit ein literal-Datenmember  
  
 Der Typ des eine [literal](../../windows/literal-cpp-component-extensions.md) Attribut sein muss, oder der Zeitpunkt der Kompilierung konvertierbar auf einen der folgenden Typen:  
  
-   Ganzzahltyp  
  
-   Zeichenfolge  
  
-   Aufzählung mit der eine ganze Zahl oder einen zugrunde liegenden Typ  
  
 Im folgende Beispiel wird C3880 generiert:  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```