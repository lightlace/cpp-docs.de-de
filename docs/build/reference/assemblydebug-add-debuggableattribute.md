---
title: "/ASSEMBLYDEBUG (DebuggableAttribute hinzuf&#252;gen)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AssemblyDebug"
  - "/ASSEMBLYDEBUG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYDEBUG (Linkeroption)"
  - "ASSEMBLYDEBUG (Linkeroption)"
  - "-ASSEMBLYDEBUG (Linkeroption)"
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYDEBUG (DebuggableAttribute hinzuf&#252;gen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYDEBUG[:DISABLE]  
```  
  
 \/ASSEMBLYDEBUG gibt das **DebuggableAttribute**\-Attribut mit der Überwachung von Debuginformationen aus und deaktiviert JIT\-Optimierungen.  Dies ist vergleichbar mit dem Festlegen des folgenden Attributs im Quellcode:  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
 \/ASSEMBLYDEBUG:DISABLE gibt das **DebuggableAttribute**\-Attribut aus, deaktiviert jedoch die Überwachung der Debuginformationen und aktiviert JIT\-Optimierungen.  Dies ist vergleichbar mit dem Festlegen des folgenden Attributs im Quellcode:  
  
```  
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE  
```  
  
 In der Standardeinstellung wird das **DebuggableAttribute**\-Attribut nicht ausgegeben.  
  
 Das **DebuggableAttribute** kann einer Assembly auch direkt im Quellcode hinzugefügt werden.  Beispiel:  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
## Hinweise  
 Bei Visual C\+\+ .NET 2003 und neueren Versionen ist es erforderlich, explizit anzugeben, dass ein verwaltetes Bild debugfähig sein muss.  Die Verwendung von [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) allein ist nicht ausreichend.  
  
 Folgende Linkeroptionen beeinflussen außerdem das Erstellen von Assemblys:  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Debuggen**.  
  
4.  Ändern Sie die Eigenschaft **Debugfähige Assembly**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)