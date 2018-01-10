---
title: COMM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COMM
dev_langs: C++
helpviewer_keywords: COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad12de948227f98ec73f779030b8e644dfad8b2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comm"></a>COMM
Erstellt eine Internetcafés Variable mit den Attributen, die im angegebenen `definition`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Hinweise  
 Jede `definition` weist folgende Form:  
  
 [[*Langtype*]] [[**NEAR** &#124; **FAR**]] *Bezeichnung***:**`type`[[**:***Anzahl*]]  
  
 Die *Bezeichnung* ist der Name der Variablen. Die `type` kann einem beliebigen Typspezifizierer ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)usw.) oder eine ganze Zahl, die die Anzahl von Bytes angibt. Die *Anzahl* gibt die Anzahl der Datenobjekte (eines ist die Standardeinstellung).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)