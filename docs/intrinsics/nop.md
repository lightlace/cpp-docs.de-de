---
title: systeminternen __nop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __nop
dev_langs: C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aecf1c0ad205d2cbf0685797cc9527f1fc4684d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="nop"></a>__nop
**Microsoft-spezifisch**  
  
 Generiert die plattformspezifischen Computercode, die keinen Vorgang ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __nop();  
```  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="remarks"></a>Hinweise  
 Die `__nop` -Funktion ist gleichbedeutend mit der `NOP` computeranweisung. Weitere Informationen zu suchen, für das Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set-Reference" auf der [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) Standort.  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__noop](../intrinsics/noop.md)