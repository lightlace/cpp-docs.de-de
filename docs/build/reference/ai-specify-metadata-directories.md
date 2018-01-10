---
title: -AI (Metadatenverzeichnisse) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs: C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e2f6cb90cd86dfc572c23ef6fd0e5661b339774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ai-specify-metadata-directories"></a>/AI (Metadatenverzeichnisse festlegen)
Gibt ein Verzeichnis an, das der Compiler durchsucht, um Dateiverweise aufzulösen, die an die `#using`-Direktive übergeben wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/AIdirectory  
```  
  
## <a name="arguments"></a>Argumente  
 `directory`  
 Das Verzeichnis oder der Pfad, den der Compiler durchsuchen soll.  
  
## <a name="remarks"></a>Hinweise  
 Nur ein Verzeichnis übergeben werden kann, um eine **/AI** aufrufen. Geben Sie einen **/AI** -Option für jeden Pfad, den der Compiler durchsuchen soll. Um beispielsweise dem compilersuchpfad für sowohl C:\Project\Meta als auch C:\Common\Meta hinzufügen `#using` Direktiven hinzufügen `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` an der Befehlszeile des Compilers oder jedes Verzeichnis zum Hinzufügen der **zusätzliche #using Verzeichnisse** die Eigenschaft in Visual Studio.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **allgemeine**.  
  
3.  Ändern der **zusätzliche #using Verzeichnisse** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [#using-Direktive](../../preprocessor/hash-using-directive-cpp.md)