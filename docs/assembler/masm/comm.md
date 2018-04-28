---
title: COMM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 111dac47089fea13febe787e5b73557b287beea8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="comm"></a>COMM
Erstellt eine Internetcafés Variable mit den Attributen, die im angegebenen `definition`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
COMM definition [[, definition]] ...  
```  
  
## <a name="remarks"></a>Hinweise  
 Jede `definition` weist folgende Form:  
  
 [[*langtype*]] [[**NEAR** &#124; **FAR**]] *label ***:**`type`[[**:*** count*]]  
  
 Die *Bezeichnung* ist der Name der Variablen. Die `type` kann einem beliebigen Typspezifizierer ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)usw.) oder eine ganze Zahl, die die Anzahl von Bytes angibt. Die *Anzahl* gibt die Anzahl der Datenobjekte (eines ist die Standardeinstellung).  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)