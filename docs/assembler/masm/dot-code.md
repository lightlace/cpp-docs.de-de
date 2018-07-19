---
title: . CODE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59e376fc9c10ab8891b02e4da334341ae0534b73
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32051230"
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