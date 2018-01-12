---
title: Compilerfehler C3880 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3880
dev_langs: C++
helpviewer_keywords: C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a1aba2a8cc76e1f47650b4a4fd4c47e95e98d2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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