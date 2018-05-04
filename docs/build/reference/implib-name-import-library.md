---
title: -IMPLIB (Name der Importbibliothek) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72edc0fcb1b216319d6f6c9924cb92a165b3196b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="implib-name-import-library"></a>/IMPLIB (Name der Importbibliothek)
  
> / IMPLIB:*Dateiname*  
  
## <a name="parameters"></a>Parameter  
  
*filename*  
Ein benutzerdefinierter Name für die Importbibliothek. Er ersetzt den Standardnamen.  
  
## <a name="remarks"></a>Hinweise  
  
Die Option/IMPLIB überschreibt den Standardnamen für die Importbibliothek, die Verknüpfung erstellt werden, wenn sie ein Programm erstellt, das Exporte enthält. Der Standardname ist aus den Basisnamen der wichtigsten Ausgabedatei und der Erweiterung gebildet. Lib. Ein Programm enthält Exporte, wenn eine oder mehrere der folgenden angegeben werden:  
  
-   Die [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) Schlüsselwort im Quellcode  
  
-   [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei  
  
-   Ein [/EXPORT](../../build/reference/export-exports-a-function.md) -Spezifikation in einem Linkbefehl  
  
 LINK ignoriert IMPLIB, wenn keine Importbibliothek erstellt wird. Wenn keine Exporte angegeben sind, erstellt LINK eine Importbibliothek nicht. Eine Exportdatei in den Build verwendet wird, geht davon aus verknüpfen, dass eine Importbibliothek ist bereits vorhanden ist und einen nicht erstellt. Informationen über Importbibliotheken und Exportdateien finden Sie unter [LIB-Referenz](../../build/reference/lib-reference.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Importbibliothek** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)