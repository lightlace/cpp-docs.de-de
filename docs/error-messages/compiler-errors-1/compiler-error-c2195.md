---
title: Compilerfehler C2195 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2195
dev_langs: C++
helpviewer_keywords: C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 557d4dd0ae0f25326fed227ab9ad508e2ebce30d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2195"></a>Compilerfehler C2195
'Bezeichner': ist ein Datensegment  
  
 Die `code_seg` -Pragma verwendet einen Segmentnamen verwendet, mit der `data_seg` Pragma.  
  
 Im folgende Beispiel wird C2195 generiert:  
  
```  
// C2195.cpp  
#pragma data_seg("MYDATA")  
#pragma code_seg("MYDATA")   // C2195  
#pragma code_seg("MYDATA2")   // OK  
```