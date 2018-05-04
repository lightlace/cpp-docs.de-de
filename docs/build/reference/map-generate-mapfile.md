---
title: -MAP (Zuordnungsdatei generieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10f4b23cf8f1c05fb8bd196dc9a6cd54971b1572
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="map-generate-mapfile"></a>/MAP (Zuordnungsdatei generieren)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Ein vom Benutzer angegebener Name für die Zuordnungsdatei ein. Er ersetzt den Standardnamen.  
  
## <a name="remarks"></a>Hinweise  
 Die Map-Option weist den Linker erstellen eine Zuordnungsdatei.  
  
 Standardmäßig den Namen des Linkers die Zuordnungsdatei mit den Namen des Programms und die Erweiterung .map. Das optionale *Filename* können Sie den Standardnamen für eine Zuordnungsdatei zu überschreiben.  
  
 Eine Zuordnungsdatei ist eine Textdatei, die die folgende Informationen zu der zu verknüpfende Programm enthält:  
  
-   Der Modulname, also der Basisname der Datei  
  
-   Der Zeitstempel aus dem Dateiheader Programm (nicht aus dem Dateisystem)  
  
-   Eine Liste der Gruppen in der Anwendung mit jeder Gruppe Startadresse (als *Abschnitt*:*Offset*), Länge, Gruppenname und -Klasse  
  
-   Eine Liste der öffentlichen Symbole, die mit jeder Adresse (als *Abschnitt*:*Offset*), Symbolnamen, Flatfile-Adresse und der OBJ-Datei, in dem das Symbol definiert ist,  
  
-   Der Einstiegspunkt (als *Abschnitt*:*Offset*)  
  
 Die [/MapInfo](../../build/reference/mapinfo-include-information-in-mapfile.md) Option gibt zusätzliche Informationen, die in der Map-Datei eingeschlossen werden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Debuggen** Eigenschaftenseite.  
  
4.  Ändern der **Zuordnungsdatei generieren** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)