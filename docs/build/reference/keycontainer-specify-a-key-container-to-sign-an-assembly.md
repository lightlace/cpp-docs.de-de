---
title: "/KEYCONTAINER (Schl&#252;sselcontainer zum Signieren einer Assembly festlegen)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.KeyContainer"
  - "/keycontainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYCONTAINER (Linkeroption)"
  - "KEYCONTAINER (Linkeroption)"
  - "-KEYCONTAINER (Linkeroption)"
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /KEYCONTAINER (Schl&#252;sselcontainer zum Signieren einer Assembly festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYCONTAINER:name  
```  
  
## Hinweise  
 wobei  
  
 *Name*  
 Der Container, der den Schlüssel enthält.  Schließen Sie die Zeichenfolge in doppelte Anführungszeichen \(" "\) ein, falls sie ein Leerzeichen enthält.  
  
## Hinweise  
 Der Linker erstellt eine signierte Assembly, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert.  Geben Sie [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file` in der Befehlszeile ein, um eine Schlüsseldatei zu erstellen.  Mit **sn \-i** wird das Schlüsselpaar in einen Container installiert.  
  
 Bei der Kompilierung mit [\/LN](../../build/reference/ln-create-msil-module.md) wird der Name der Schlüsseldatei im Modul beibehalten und in eine Assembly eingefügt. Letztere wird erstellt, wenn Sie eine Assembly, die einen expliziten Verweis auf das Modul enthält, mittels [\#using](../../preprocessor/hash-using-directive-cpp.md) kompilieren oder eine Verknüpfung mit [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) herstellen.  
  
 Die Verschlüsselungsinformationen können auch mit [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) an den Compiler übergeben werden.  Verwenden Sie [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), wenn die Assembly teilweise signiert werden soll.  Weitere Informationen über das Signieren einer Assembly finden Sie unter [Assemblys mit starken Namen \(Assemblysignierung\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Folgende Linkeroptionen beeinflussen außerdem das Erstellen von Assemblys:  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)