---
title: "/HIGHENTROPYVA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA editbin-Option"
  - "HIGHENTROPYVA editbin-Option"
  - "-HIGHENTROPYVA editbin-Option"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob das ausführbare Image 64\-bit\-ASLR mit hoher Entropie unterstützt.  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## Hinweise  
 Mit dieser Option wird der Header einer DLL\- oder EXE\-Datei geändert, um anzugeben, ob ASLR mit 64\-Bit\-Adressen unterstützt wird.  Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64\-Bit\-ASLR unterstützendes Betriebssystem die Segmente des ausführbaren Images zur Ladezeit umbasieren, indem zufällige Adressen in einem virtuellen 64\-Bit\-Adressbereich verwendet werden.  Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Standardmäßig legt der Linker diese Option für ausführbare 64\-Bit\-Images fest.  Zum Festlegen dieser Option muss auch die [\/DYNAMICBASE](../../build/reference/dynamicbase.md)\-Option festgelegt werden.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows\-ISV\-Softwaresicherheitsmaßnahmen](http://msdn.microsoft.com/library/bb430720.aspx)