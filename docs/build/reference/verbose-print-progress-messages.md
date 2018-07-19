---
title: -VERBOSE (Statusmeldungen ausgeben) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
dev_langs:
- C++
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee1bf99cdf27e432bf8bdf6b7c0e48a84aeaac21
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377468"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (Statusmeldungen ausgeben)
```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Linker sendet Informationen über den Status des Verknüpfungsvorgangs an das **Ausgabe** Fenster. Auf Befehlszeilenebene werden die Informationen an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|/VERBOSE|Zeigt Einzelheiten über den Verknüpfungsvorgang an.|  
|/VERBOSE:ICF|Anzeigen von Informationen über die Linkeraktivität an, die durch die Verwendung von entsteht [/OPT: ICF](../../build/reference/opt-optimizations.md).|  
|/VERBOSE:INCR|Zeigt Informationen über den inkrementellen Verknüpfungsvorgang an.|  
|/VERBOSE:LIB|Zeigt Statusmeldungen an, die sich nur auf die durchsuchten Bibliotheken beziehen.<br /><br /> Die angezeigten Informationen schließen das Durchsuchen von Bibliotheken ein und führen jeden Bibliotheks- und Objektnamen (mit vollständigem Pfad), das Symbol, das durch die Bibliothek aufgelöst wird, und eine Liste der Objekte auf, die auf das Symbol verweisen.|  
|/VERBOSE:REF|Zeigt Informationen über die Linkeraktivität an, die durch die Verwendung von entsteht [/OPT: REF](../../build/reference/opt-optimizations.md).|  
|/VERBOSE:SAFESEH|Zeigt Informationen zu Modulen, die nicht kompatibel mit der sicheren Ausnahmebehandlung bei sind [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) nicht angegeben wird.|  
|/VERBOSE:UNUSEDLIBS|Zeigt Informationen über alle Bibliotheksdateien an, die nicht verwendet werden, wenn das Image erstellt wird.|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Linker** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Fügen Sie die Option aus, um die **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)