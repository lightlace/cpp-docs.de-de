---
title: -DYNAMICBASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7a4cf7aa35d7ad6b41fc6d61f3f27662ae2c8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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