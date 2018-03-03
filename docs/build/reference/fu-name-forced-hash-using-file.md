---
title: '-FU (Name Forced #using-Datei) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs:
- C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17b62859aaf0c9dc6b3313fbb726602b5b83a82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fu-name-forced-using-file"></a>/FU (Name der expliziten #using-Datei)
Eine Compileroption, mit denen Sie als Alternative zum Übergeben eines Dateinamens, [#using-Direktive](../../preprocessor/hash-using-directive-cpp.md) im Quellcode.  
  
## <a name="syntax"></a>Syntax  
  
```  
/FU file  
```  
  
## <a name="arguments"></a>Argumente  
 `file`  
 Gibt die Metadatendatei, die in dieser Kompilierung zu verweisen.  
  
## <a name="remarks"></a>Hinweise  
 Der Schalter/fu akzeptiert nur einen Dateinamen an. Um mehrere Dateien anzugeben, verwenden Sie/fu mit jeweils ein.  
  
 Bei Verwendung von [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] und Metadaten mit Verweisen auf die [Friend-Assemblys](../../dotnet/friend-assemblies-cpp.md) Funktion, Sie können keine **/FU**. Sie müssen die Metadaten im Code verweisen, indem `#using`– zusammen mit den `[as friend]` Attribut. Friend-Assemblys werden nicht unterstützt, [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]).  
  
 Weitere Informationen dazu, wie eine Assembly oder ein Modul für die common Language Runtime (CLR) zu erstellen, finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md). Informationen zum Erstellen in [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], finden Sie unter [Erstellen von apps und Bibliotheken](../../cppcx/building-apps-and-libraries-c-cx.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **erweitert** Eigenschaftenseite.  
  
4.  Ändern der **Force #using** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)