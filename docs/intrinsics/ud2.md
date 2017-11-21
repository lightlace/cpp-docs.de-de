---
title: __ud2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ud2
dev_langs: C++
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 699e575d283f830d94c123f7748f7fdaa6272ff5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ud2"></a>__ud2
**Microsoft-spezifisch**  
  
 Generiert eine nicht definierte Anweisung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __ud2();  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Prozessor wird eine ungültige Opcode-Ausnahme auslöst, wenn Sie eine nicht definierte Anweisung auszuführen.  
  
 Die `__ud2` -Funktion ist gleichbedeutend mit dem `UD2` computeranweisung und ist nur im Kernelmodus verfügbar. Weitere Informationen zu suchen, für das Dokument "Intel Architecture-Softwareentwickler manuell, Volume 2: Instruction Set-Reference" auf der [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine nicht definierte-Anweisung, die eine Ausnahme auslöst. Der Ausnahmehandler ändert dann den Rückgabecode von null bis eins.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
```Output  
Before __ud2(). Return code = 0.  
  In the exception handler.  
After __ud2().  Return code = 1.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)