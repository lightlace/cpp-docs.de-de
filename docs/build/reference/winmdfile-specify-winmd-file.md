---
title: -WINMDFILE (Winmd-Datei angeben) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eaf1bfc805db568a012c28d66361bbd99745a95
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375596"
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