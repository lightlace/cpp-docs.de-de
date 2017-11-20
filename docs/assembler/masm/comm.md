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
ms.openlocfilehash: b8feb74f1da11fb6c4205ec1d8381f78789f684f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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