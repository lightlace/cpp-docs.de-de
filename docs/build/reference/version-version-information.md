---
title: -VERSION (Versionsinformationen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs: C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6a0792a3895aac2887e635cb300f8ba9fde67e97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="version-version-information"></a>/VERSION (Versionsinformationen)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *wichtige*und *Nebenversion*  
 Die Versionsnummer im Header des .exe oder .dll-Datei die gewünschten.  
  
## <a name="remarks"></a>Hinweise  
 Die/Version-Option weist den Linker an, eine Versionsnummer im Header der .exe oder .dll-Datei zu speichern. Verwenden von DUMPBIN [/Headers](../../build/reference/headers.md) an das Bildfeld Version der OPTIONALEN HEADERWERTE, die Auswirkung von/Version anzuzeigen.  
  
 Die *wichtigen* und *kleinere* Argumente sind Dezimalzahlen im Bereich von 0 bis 65.535. Der Standardwert ist 0,0-Version.  
  
 Die Informationen, die mit/Version angegeben wirkt sich nicht auf die Versionsinformationen aus, die für eine Anwendung angezeigt wird, wenn Sie seine Eigenschaften im Datei-Explorer anzeigen. Diese Informationen stammen aus einer Ressourcendatei, die zum Erstellen der Anwendung verwendet wird. Finden Sie unter [Versionsinfo-Editor](../../windows/version-information-editor.md) für Weitere Informationen.  
  
 Eine weitere Möglichkeit zum Einfügen einer Versionsnummer wird mit der [VERSION](../../build/reference/version-c-cpp.md) Moduldefinition Anweisung.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **allgemeine** Eigenschaftenseite.  
  
4.  Ändern der **Version** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)