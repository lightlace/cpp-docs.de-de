---
title: EXTERNDEF | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EXTERNDEF
dev_langs: C++
helpviewer_keywords: EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64aa9cc69825ef1f932024bc45c051e16c99e2eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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