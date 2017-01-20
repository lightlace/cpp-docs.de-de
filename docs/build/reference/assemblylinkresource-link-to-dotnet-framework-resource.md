---
title: "/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verkn&#252;pfen)"
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
  - "/ASSEMBLYLINKRESOURCE"
  - "VC.Project.VCLinkerTool.AssemblyLinkResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYLINKRESOURCE (Linkeroption)"
  - "ASSEMBLYLINKRESOURCE (Linkeroption)"
  - "-ASSEMBLYLINKRESOURCE (Linkeroption)"
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verkn&#252;pfen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 die .NET Framework\-Ressourcendatei, zu der Sie von der Assembly aus eine Verknüpfung erstellen möchten.  
  
## Hinweise  
 Die \/ASSEMBLYLINKRESOURCE\-Option erstellt einen Link zu einer .NET Framework\-Ressource in der Ausgabedatei. Die Ressourcendatei wird nicht in der Ausgabedatei platziert.  [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) bettet eine Ressourcendatei in der Ausgabedatei ein.  
  
 Verknüpfte Ressourcen sind in der Assembly öffentlich, wenn sie mit dem Linker erstellt wurden.  
  
 \/ASSEMBLYLINKRESOURCE erfordert die Verwendung von [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) in der Kompilierung. [\/LN](../../build/reference/ln-create-msil-module.md) oder [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) sind in Verbindung mit \/ASSEMBLYLINKRESOURCE nicht zulässig.  
  
 Wenn *filename* einer .NET Framework\-Ressourcendatei entspricht, die beispielsweise durch [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) oder in der Entwicklungsumgebung erstellt wurde, kann mit Membern im **System.Resources**\-Namespace darauf zugegriffen werden.  Weitere Informationen finden Sie unter [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx).  Für alle anderen Ressourcen verwenden Sie die **GetManifestResource**\*\-Methoden in der **System.Reflection.Assembly**\-Klasse, um die Ressource zur Laufzeit aufzurufen.  
  
 *filename* kann ein beliebiges Dateiformat sein.  Möglicherweise möchten Sie eine systemeigene DLL in die Assembly aufnehmen, damit sie im globalen Assemblycache installiert werden kann und damit von verwaltetem Code in der Assembly darauf zugegriffen werden kann.  
  
 Folgende Linkeroptionen beeinflussen außerdem das Erstellen von Assemblys:  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
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