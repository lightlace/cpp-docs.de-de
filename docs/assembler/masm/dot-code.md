---
title: . CODE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .CODE
dev_langs: C++
helpviewer_keywords: .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 150b5a0c26be3c3c4d0412157179ebfcbec128e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="code"></a>.CODE
Bei Verwendung mit [. Modell](../../assembler/masm/dot-model.md), gibt den Anfang ein Codesegment.  
  
## <a name="syntax"></a>Syntax  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`name`|Optionaler Parameter, der den Namen des Codesegments angibt. Der Standardname lautet _TEXT für kleine, "klein", kompakte und flachen [Modelle](../../assembler/masm/dot-model.md). Der Standardname lautet *"ModuleName"*_TEXT für andere Modelle.|  
  
## <a name="see-also"></a>Siehe auch  
 [Direktiven – Referenz](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)