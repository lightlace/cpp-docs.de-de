---
title: Compilerfehler C2850 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2850
dev_langs: C++
helpviewer_keywords: C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac2619417a55d5125863eb7ffd7ef45e09a2d742
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2850"></a>Compilerfehler C2850
'construct': nur im Dateigültigkeitsbereich; zulässig. in einer geschachtelten Konstrukts möglicherweise nicht  
  
 Konstrukte, z. B. einige Pragmas können nur im globalen Gültigkeitsbereich angezeigt werden.  
  
 Im folgende Beispiel wird C2850 generiert:  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```