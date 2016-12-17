---
title: "/ASSEMBLYMODULE (MSIL-Modul zur Assembly hinzuf&#252;gen)"
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
  - "/assemblymodule"
  - "VC.Project.VCLinkerTool.AddModuleNamesToAssembly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYMODULE (Linkeroption)"
  - "Assemblys [C++]"
  - "Assemblys [C++], Hinzufügen von Modulen zu"
  - "ASSEMBLYMODULE (Linkeroption)"
  - "-ASSEMBLYMODULE (Linkeroption)"
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYMODULE (MSIL-Modul zur Assembly hinzuf&#252;gen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYMODULE:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 Das Modul, das in diese Assembly eingefügt werden soll.  
  
## Hinweise  
 Mithilfe der \/ASSEMBLYMODULE\-Option können Sie einer Assembly einen Modulverweis hinzufügen.  Typinformationen im Modul sind für das Assemblyprogramm, das den Modulverweis hinzugefügt hat, nicht verfügbar.  Typinformationen im Modul sind jedoch für alle Programme verfügbar, die auf die Assembly verweisen.  
  
 Mit [\#using](../../preprocessor/hash-using-directive-cpp.md) können Sie sowohl einen Modulverweis in eine Assembly einfügen als auch die Typinformationen des Moduls im Assemblyprogramm verfügbar machen.  
  
 Beispiel:  
  
1.  Erstellen Sie ein Modul mit [\/LN](../../build/reference/ln-create-msil-module.md).  
  
2.  In einem anderen Projekt fügen Sie mit **\/ASSEMBLYMODULE** das Modul in die aktuelle Kompilierung ein, wodurch eine Assembly generiert wird.  In diesem Projekt wird anhand von `#using` nicht auf das Modul verwiesen.  
  
3.  In Projekten mit Verweis auf diese Assembly ist dann auch die Verwendung von Typen des Moduls möglich.  
  
 Folgende Linkeroptionen beeinflussen außerdem das Erstellen von Assemblys:  
  
-   [\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Der Visual C\+\+\-Linker akzeptiert .netmodule\-Dateien, als Eingabe und der Ausgabedatei erzeugt vom Linker eine Assembly oder .netmodule ohne Ablaufabhängigkeit auf einem der .netmodules ist, die als Eingabe für den Linker wurden.  Weitere Informationen finden Sie unter [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Ändern Sie die Eigenschaft **Modul zur Assembly hinzufügen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)