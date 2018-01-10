---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dynamicbase
dev_langs: C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07fd3c89cb2cff1fed06189ac66b2e67f7e52ade
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dynamicbase"></a>/DYNAMICBASE
Gibt an, ob ein ausführbares Image generiert werden soll, für das zur Ladezeit mit ASLR (Address Space Layout Randomization) nach dem Zufallsprinzip ein Rebase ausgeführt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig legt der Linker die **"/ DynamicBase"** Option.  
  
 Diese Option ändert den Header eines ausführbaren Images, um anzugeben, ob das Ladeprogramm nach dem Zufallsprinzip zur Ladezeit ein Rebase des Images ausführen kann.  
  
 ASLR wird unter Windows Vista, Windows Server 2008, Windows 7, Windows 8 und Windows Server 2012 unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)   
 [Windows ISV-Softwaresicherheit](http://msdn.microsoft.com/library/bb430720.aspx)