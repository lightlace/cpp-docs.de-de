---
title: EXTERNDEF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b010f52f91a04388f34052fcc5c374690cff13df
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="externdef"></a>EXTERNDEF
Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole, so genannte *Namen* , dessen Typ `type`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn *Namen* ist definiert in das Modul wird dies als behandelt [öffentlichen](../../assembler/masm/public-masm.md). Wenn *Namen* verwiesen wird im Modul, wird dies als behandelt ["extern"](../../assembler/masm/extern-masm.md). Wenn *Namen* ist nicht auf die verwiesen wird, wird ignoriert. Die `type` kann [ABS](../../assembler/masm/operator-abs.md), welche Importe *Namen* als Konstante. Normalerweise verwendeten Dateien einschließt.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)