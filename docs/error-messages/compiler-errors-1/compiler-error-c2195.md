---
title: Compilerfehler C2195 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2195
dev_langs:
- C++
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 979dcfee8733a7e575170c36e90ec36bbd4ff154
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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