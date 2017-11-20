---
title: -HIGHENTROPYVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /HIGHENTROPYVA
dev_langs: C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 189344645cff785b2957131303cabbe1946954ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="highentropyva"></a>/HIGHENTROPYVA
Gibt an, ob das ausführbare Image 64-bit-ASLR mit hoher Entropie unterstützt.  
  
```  
  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit dieser Option wird der Header einer DLL- oder EXE-Datei geändert, um anzugeben, ob ASLR mit 64-Bit-Adressen unterstützt wird. Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64-Bit-ASLR unterstützendes Betriebssystem die Segmente des ausführbaren Images zur Ladezeit umbasieren, indem zufällige Adressen in einem virtuellen 64-Bit-Adressbereich verwendet werden. Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Standardmäßig legt der Linker diese Option für ausführbare 64-Bit-Images fest. Zum Festlegen dieser Option die ["/ DynamicBase"](../../build/reference/dynamicbase.md) Option muss auch festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)   
 [/ DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV-Softwaresicherheit](http://msdn.microsoft.com/library/bb430720.aspx)