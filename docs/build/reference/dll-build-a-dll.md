---
title: -DLL (DLL erstellen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dll
dev_langs:
- C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1767ac9ef063ace2ee9d567dd9038519afababf8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="dll-build-a-dll"></a>/DLL (DLL erstellen)
```  
/DLL  
```  
  
## <a name="remarks"></a>Hinweise  
 Die/DLL-Option erstellt eine DLL, wie die Haupt-Ausgabedatei. Eine DLL-Datei enthält normalerweise Exporte, die von einem anderen Programm verwendet werden können. Es gibt drei Methoden zum Angeben von Exports, aufgelistet in empfohlener Reihenfolge von Nutzen:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode  
  
2.  Ein [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei  
  
3.  Ein [/EXPORT](../../build/reference/export-exports-a-function.md) -Spezifikation in einem Linkbefehl  
  
 Ein Programm kann mehr als eine Methode verwendet werden.  
  
 Eine weitere Möglichkeit zum Erstellen einer DLL wird mit der **Bibliothek** Moduldefinition Anweisung. Die Optionen "/ Base" und "/ DLL beieinander liegen, entspricht die **Bibliothek** Anweisung.  
  
 Geben Sie diese Option in der Entwicklungsumgebung nicht; Diese Option ist nur in der Befehlszeile angegeben. Diese Option wird festgelegt, wenn Sie ein DLL-Projekt mit einer Anwendungs-Assistenten erstellen.  
  
 Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL übergeben werden wie bei der Erstellung der Importbibliothek her.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Konfigurationseigenschaften** Ordner.  
  
3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.  
  
4.  Ändern der **Konfigurationstyp** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)