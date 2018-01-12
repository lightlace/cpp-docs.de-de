---
title: -WINMDFILE (Winmd-Datei angeben) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs: C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 153e5c0bd42b6fdba59e309483f25f09b86fe9fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd-Datei angeben)
Gibt den Dateinamen für die Windows-Runtime-Metadatendatei (.winmd)-Ausgabedatei, die von generiert die [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) (Linkeroption).  
  
```  
/WINMDFILE:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie den Wert, der im angegebenen `filename` zum Überschreiben des Standardnamens winmd-Datei (`binaryname`winmd). Beachten Sie, dass Sie keine ".winmd" zum Anfügen `filename`.  Wenn mehrere Werte aufgeführt sind, auf die **/WINMDFILE** Befehlszeile zum letzten Blatt hat Vorrang vor.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.  
  
4.  In der **Windows-Metadatendatei** Geben Sie den Dateispeicherort.  
  
## <a name="see-also"></a>Siehe auch  
 [/ WINMD (Windows-Metadaten generieren)](../../build/reference/winmd-generate-windows-metadata.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)