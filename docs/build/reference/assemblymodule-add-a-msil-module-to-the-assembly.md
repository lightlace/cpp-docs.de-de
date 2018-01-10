---
title: "-ASSEMBLYMODULE (Hinzufügen von MSIL-Modul zur Assembly) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs: C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efe45bd6a3225f50e1f842c6d247aae9626302a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (MSIL-Modul zur Assembly hinzufügen)
```  
/ASSEMBLYMODULE:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Das Modul aus, die in dieser Assembly enthalten sein sollen.  
  
## <a name="remarks"></a>Hinweise  
 Mit der Option/ASSEMBLYMODULE können Sie einen Modulverweis auf eine Assembly hinzufügen. Typinformationen in das Modul wird für das Assemblyprogramm nicht verfügbar, die den Modulverweis hinzugefügt. Allerdings wird Typinformationen in das Modul für jedes Programm verfügbar sein, die die Assembly verweist.  
  
 Verwendung [#using](../../preprocessor/hash-using-directive-cpp.md) , einen Modulverweis auf eine Assembly hinzuzufügen und Typinformationen für das Modul der Assemblyprogramm zur Verfügung stellen.  
  
 Betrachten Sie beispielsweise das folgende Szenario:  
  
1.  Erstellen Sie ein Modul mit [/ln](../../build/reference/ln-create-msil-module.md).  
  
2.  Verwenden Sie ASSEMBLYMODULE in einem anderen Projekt, um das Modul in der aktuellen Kompilierung einzuschließen, die eine Assembly zu erstellen. Dieses Projekt wird nicht auf das Modul mit verwiesen `#using`.  
  
3.  Jedes Projekt, das diese Assembly verweist kann jetzt auch die Typen aus dem Modul verwenden.  
  
 Andere Optionen des Linkers, die beeinflussen Generieren der Assembly sind:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Der Visual C++-Linker NETMODULE-Dateien als Eingabe akzeptiert und die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf die NETMODULE-Dateien, die an den Linker eingegeben wurden.  Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Eingabe** Eigenschaftenseite.  
  
4.  Ändern der **Modul zur Assembly hinzufügen** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)