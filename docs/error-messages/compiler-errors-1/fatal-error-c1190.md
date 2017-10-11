---
title: Schwerwiegender Fehler C1190 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1190
dev_langs:
- C++
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1b04b08bd57a527145cafde1073430a78d68b89b
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1190"></a>Schwerwiegender Fehler C1190
Für verwalteten Zielcode ist eine /clr-Option erforderlich.  
  
 Sie verwenden CLR-Konstrukte, aber Sie haben keine **/clr**angegeben.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Im folgenden Beispiel wird C1190 generiert:  
  
```  
// C1190.cpp  
// compile with: /c  
__gc class A {};   // C1190  
ref class A {};  
```
