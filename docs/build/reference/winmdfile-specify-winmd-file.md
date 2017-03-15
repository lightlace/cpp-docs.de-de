---
title: "/WINMDFILE (winmd-Datei angeben) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadataFile"
dev_langs: 
  - "C++"
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDFILE (winmd-Datei angeben)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Dateinamen für die Ausgabedatei der Windows \(.winmd Runtime\-Metadaten\) an, die durch die [\/WINMD](../../build/reference/winmd-generate-windows-metadata.md) Linkeroption generiert wird.  
  
```  
  
/WINMDFILE:filename  
  
```  
  
## Hinweise  
 Verwenden Sie den Wert, der in `filename` bereitgestellt wird, um den Dateinamen des standardmäßigen .winmd \(`binaryname`.winmd\) zu überschreiben.  Beachten Sie, dass Sie ".winmd" nicht in `filename` anfügen. Wenn mehrere Werte auf der Befehlszeile **\/WINMDFILE** aufgeführt sind, hat der letzte Suchvorgang Vorrang.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Windows\-Metadaten** aus.  
  
4.  Im Feld **Windows\-Metadatendatei** den Speicherort ein.  
  
## Siehe auch  
 [\/WINMD \(Windows\-Metadaten generieren\)](../../build/reference/winmd-generate-windows-metadata.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)