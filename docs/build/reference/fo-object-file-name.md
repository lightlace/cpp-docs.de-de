---
title: -Fo (Name der Objektdatei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea552b149270b8e644140a4dd51f220648ef376e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fo-object-file-name"></a>/Fo (Name der Objektdatei)
Gibt einen Namen für die Objektdatei (OBJ) oder das Verzeichnis an, der anstelle des Standardwerts verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Fopathname  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option nicht verwenden, wird die Objektdatei der Basisname der Quelldatei und die Erweiterung .obj verwendet. Können Sie Name und Erweiterung werden sollen, aber die empfohlene Konvention ist die Verwendung. Objekt  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien** .  
  
4.  Ändern der **Name der Objektdatei** Eigenschaft.  In der Entwicklungsumgebung vornehmen, muss die Objektdatei haben die Erweiterung. Objekt  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile erstellt eine Objektdatei namens THIS.obj in ein vorhandenes Verzeichnis \OBJECT auf Laufwerk B.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)