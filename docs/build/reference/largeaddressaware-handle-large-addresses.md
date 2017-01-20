---
title: "/LARGEADDRESSAWARE (Umfangreiche Adressen verarbeiten)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LargeAddressAware"
  - "/largeaddressaware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LARGEADDRESSAWARE (Linkeroption)"
  - "LARGEADDRESSAWARE (Linkeroption)"
  - "-LARGEADDRESSAWARE (Linkeroption)"
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /LARGEADDRESSAWARE (Umfangreiche Adressen verarbeiten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## Hinweise  
 Die \/LARGEADDRESSAWARE\-Option teilt dem Linker mit, dass die Anwendung Adressen, die größer sind als 2 Gigabyte, verarbeiten kann.  In den 64\-Bit\-Compilern ist diese Option standardmäßig aktiviert.  In den 32\-Bit\-Compilern wird \/LARGEADDRESSAWARE:NO aktiviert, wenn für \/LARGEADDRESSAWARE nichts anderes in der Linkerzeile angegeben wurde.  
  
 Wenn eine Anwendung mit **\/LARGEADDRESSAWARE** verknüpft wurde, zeigt **DUMPBIN**[\/HEADERS](../../build/reference/headers.md) diesbezüglich weitere Informationen an.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **System**.  
  
4.  Ändern Sie die Eigenschaft **Große Adressen aktivieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)