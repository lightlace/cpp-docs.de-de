---
title: "/HIGHENTROPYVA (Unterst&#252;tzung f&#252;r 64-Bit ASLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# /HIGHENTROPYVA (Unterst&#252;tzung f&#252;r 64-Bit ASLR)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass das ausführbare Image 64\-Bit\-ASLR mit hoher Entropie unterstützt.  
  
## Syntax  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## Hinweise  
 Standardmäßig ist "\/HIGHENTROPYVA" für ausführbare 64\-Bit\-Images aktiviert.  Auf ausführbare 32\-Bit\-Images ist die Option nicht anwendbar.  Um diese Option zu aktivieren, muss auch "\/DYNAMICBASE" aktiviert sein.  
  
 Mit "\/HIGHENTROPYVA" wird der Header einer DLL\- oder EXE\-Datei geändert, um anzugeben, ob ASLR mit 64\-Bit\-Adressen unterstützt wird.  Wenn diese Option auf einer ausführbaren Datei und allen Modulen festgelegt wird, von denen sie abhängt, kann ein 64\-Bit\-ASLR unterstützendes Betriebssystem die Segmente des ausführbaren Images zur Ladezeit umbasieren, indem zufällige Adressen in einem virtuellen 64\-Bit\-Adressbereich verwendet werden.  Aufgrund dieses großen Adressbereichs ist es für einen Angreifer schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
5.  Geben Sie unter **Zusätzliche Optionen**die Option `/HIGHENTROPYVA` oder `/HIGHENTROPYVA:NO` ein.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)