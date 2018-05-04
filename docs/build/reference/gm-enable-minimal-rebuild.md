---
title: -Gm (minimale Neuerstellung aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs:
- C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e0b83c34b0ff8cacbca9d21a40c6c9572f516d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (Minimale Neuerstellung aktivieren)
Aktiviert die minimale Neuerstellung, die bestimmt, ob C++-Quelldateien, die geänderte C++-Klassendefinitionen enthalten (gespeichert in Headerdateien (.h)) neu kompiliert werden müssen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Gm  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler speichert Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen während der ersten Kompilierung in der .idb-Datei des Projekts. (Abhängigkeitsinformationen gibt an, welche Quelldatei die Klassendefinition abhängig ist, und welche .h-Datei die Definition befindet sich im.) Nachfolgende Kompilierungen ein, die anhand der Informationen, die in der .idb-Datei gespeichert, um zu bestimmen, ob eine Quelldatei kompiliert werden muss, auch wenn es sich um eine geänderte .h-Datei enthält.  
  
> [!NOTE]
>  Die minimale Neuerstellung basiert auf Klassendefinitionen, die sich zwischen Includedateien nicht ändern. Klassendefinitionen müssen für ein Projekt global sein (es sollte nur eine Definition für eine bestimmte Klasse vorhanden sein), da die Abhängigkeitsinformationen in der .idb-Datei für das gesamte Projekt erstellt werden. Wenn Sie mehr als eine Definition für eine Klasse in Ihrem Projekt haben, deaktivieren Sie die minimale Neuerstellung.  
  
 Da der Linker inkrementelle nicht die Windows-Metadaten in der OBJ-Dateien mithilfe von eingeschlossen unterstützt die [/ZW (Windows-Runtime-Kompilierung)](../../build/reference/zw-windows-runtime-compilation.md) -Option der **/GM** -Option ist nicht kompatibel mit  **/ ZW**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern der **minimale Neuerstellung aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)