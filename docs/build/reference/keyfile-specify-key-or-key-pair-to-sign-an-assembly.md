---
title: "/KEYFILE (Schl&#252;sselcontainer oder Schl&#252;sselpaar zum Signieren einer Assembly festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
  - "VC.Project.VCLinkerTool.KeyFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE (Linkeroption)"
  - "KEYFILE (Linkeroption)"
  - "-KEYFILE (Linkeroption)"
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /KEYFILE (Schl&#252;sselcontainer oder Schl&#252;sselpaar zum Signieren einer Assembly festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYFILE:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 Die Datei, die den Schlüssel enthält.  Schließen Sie die Zeichenfolge in doppelte Anführungszeichen \(" "\) ein, falls sie ein Leerzeichen enthält.  
  
## Hinweise  
 Der Linker fügt den öffentlichen Schlüssel in das Assemblymanifest ein und signiert dann die endgültige Assembly mit dem privaten Schlüssel.  Geben Sie [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file` in der Befehlszeile ein, um eine Schlüsseldatei zu erstellen.  Namen signierter Assemblys werden als starke Namen bezeichnet.  
  
 Bei der Kompilierung mit [\/LN](../../build/reference/ln-create-msil-module.md) wird der Name der Schlüsseldatei im Modul beibehalten und in eine Assembly eingefügt. Letztere wird erstellt, wenn Sie eine Assembly, die einen expliziten Verweis auf das Modul enthält, mittels [\#using](../../preprocessor/hash-using-directive-cpp.md) kompilieren oder eine Verknüpfung mit [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) herstellen.  
  
 Die Verschlüsselungsinformationen können auch mit [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) an den Linker übergeben werden.  Verwenden Sie [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md), wenn die Assembly teilweise signiert werden soll.  Weitere Informationen über das Signieren einer Assembly finden Sie unter [Assemblys mit starken Namen \(Assemblysignierung\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Falls sowohl **\/KEYFILE** als auch **\/KEYCONTAINER** angegeben werden \(entweder als Befehlszeilenoption oder als benutzerdefiniertes Attribut\), versucht der Linker zunächst, Daten vom Schlüsselcontainer abzurufen.  Wenn dies erfolgreich ist, wird die Assembly mit den Informationen aus dem Schlüsselcontainer signiert.  Wenn der Schlüsselcontainer nicht gefunden wird, versucht der Linker, Daten aus der mit **\/KEYFILE** festgelegten Datei abzurufen.  Ist dies erfolgreich, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden in den Schlüsselcontainer installiert \(ähnlich wie mit sn \-i\), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.  
  
 Beachten Sie, dass eine Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.  
  
 Weitere Informationen über das Signieren einer Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
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