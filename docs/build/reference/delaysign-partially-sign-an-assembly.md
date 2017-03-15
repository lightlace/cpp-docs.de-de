---
title: "/DELAYSIGN (Assembly teilweise signieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
  - "VC.Project.VCLinkerTool.DelaySign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYSIGN (Linkeroption)"
  - "DELAYSIGN (Linkeroption)"
  - "-DELAYSIGN (Linkeroption)"
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYSIGN (Assembly teilweise signieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYSIGN[:NO]  
```  
  
## Hinweise  
 wobei  
  
 NO  
 bewirkt, dass die Assembly nicht teilweise signiert wird.  
  
## Hinweise  
 Verwenden Sie **\/DELAYSIGN**, wenn Sie nur den öffentlichen Schlüssel in die Assembly einfügen möchten.  Der Standardwert lautet **\/DELAYSIGN:NO**.  
  
 Die Option **\/DELAYSIGN** ist nur wirksam, wenn sie mit [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) oder [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) verwendet wird.  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, hasht der Compiler die Datei, die das Manifest \(die Assemblymetadaten\) enthält und signiert dieses Hash mit dem privaten Schlüssel.  Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.  Wenn eine Assembly verzögert signiert wird, berechnet und speichert der Linker die Signatur nicht, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Mithilfe von **\/DELAYSIGN** kann ein Testprogramm die Assembly z. B. in den globalen Cache einfügen.  Nach dem Testen können Sie die Assembly vollständig signieren, indem Sie den privaten Schlüssel in der Assembly platzieren.  
  
 Weitere Informationen über das Signieren einer Assembly finden Sie unter [Assemblys mit starken Namen \(Assemblysignierung\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) und [Verzögertes Signieren einer Assembly](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
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