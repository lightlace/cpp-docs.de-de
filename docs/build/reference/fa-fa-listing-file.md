---
title: "/FA, /Fa (Listendatei) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AssemblerListingLocation"
  - "VC.Project.VCCLCompilerTool.ConfigureASMListing"
  - "VC.Project.VCCLWCECompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.AssemblerListingLocation"
  - "/fa"
  - "VC.Project.VCCLCompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FA (Compileroption) [C++]"
  - "Nur die Assembly auflisten"
  - "FA (Compileroption) [C++]"
  - "-FA (Compileroption) [C++]"
  - "Auflisten des Dateityps"
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /FA, /Fa (Listendatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Listendatei, die Assemblycode enthält  
  
## Syntax  
  
```  
/FA[c|s|u]  
/Fapathname  
```  
  
## Hinweise  
 Die Argumente legen die Erzeugung von Quell\- und Maschinencode und die Erweiterung der Listendatei wie folgt fest:  
  
 In der folgenden Tabelle sind die verschiedenen Werte für **\/FA** beschrieben.  Es besteht die Möglichkeit, mehr als einen Wert für **\/FA** anzugeben.  Sie können beispielsweise **\/FAsu** angeben.  
  
|Option|Listeninhalt und Dateierweiterung|  
|------------|---------------------------------------|  
|**\/FA**|Assemblycode; ASM|  
|**\/FAc**|Maschinen\- und Assemblycode; COD|  
|**\/FAs**|Quell\- und Assemblycode; ASM<br /><br /> Wenn **\/FAcs** angegeben wird, wird als Dateierweiterung .cod verwendet.|  
|**\/FAu**|Führt dazu, dass die Ausgabedatei im UTF\-8\-Format mit einer Bytereihenfolgenmarkierung erstellt wird.  In der Standardeinstellung wird die Datei mit ANSI codiert. Sie sollten jedoch **\/FAu** verwenden, wenn Sie eine Listendatei erstellen möchten, die auf jedem System ordnungsgemäß dargestellt wird, oder wenn Sie für die Eingabe in den Compiler Quellcodedateien im Unicode\-Format verwenden.<br /><br /> Wenn **\/FAsu** angegeben wird, und wenn eine Quellcodedatei in einem von UTF\-8 verschiedenem Unicode\-Format codiert ist, werden die Codezeilen in der .asm\-Datei unter Umständen nicht ordnungsgemäß dargestellt.|  
  
 Standardmäßig erhält die Listendatei denselben Basisnamen wie die Quelldatei.  Sie können den Namen der Listendatei und des Verzeichnisses, in dem sie erstellt wird, mithilfe der **\/Fa**\-Option ändern.  
  
|Verwendung von \/Fa|Ergebnis|  
|-------------------------|--------------|  
|**\/Fa**|Ein *source\_file*.asm wird für alle Quellcodedateien in der Kompilierung angelegt.|  
|**\/Fa** *filename*|*filename*.asm wird im aktuellen Verzeichnis abgelegt.  Nur beim Kompilieren einer einzelnen Quellcodedatei gültig.|  
|**\/Fa** *filename.extension*|*filename.extension* wird im aktuellen Verzeichnis abgelegt.  Nur beim Kompilieren einer einzelnen Quellcodedatei gültig.|  
|**\/Fa** *directory*\\|Ein *source\_file*.asm wird in angegebene *directory* für alle Quellcodedateien in der Kompilierung erzeugt und eingefügt.  Beachten Sie, dass ein nachgestellter umgekehrter Schrägstrich erforderlich ist.  Nur Pfade auf der aktuellen Festplatte sind zulässig.|  
|**\/Fa** *directory*\\*filename*|*filename* angegebene .asm wird in `directory` abgelegt.  Nur beim Kompilieren einer einzelnen Quellcodedatei gültig.|  
|**\/Fa** *directory*\\*filename.extension*|*filename.extension* angegebene wird in `directory` abgelegt.  Nur beim Kompilieren einer einzelnen Quellcodedatei gültig.|  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Ausgabedateien**.  
  
4.  Ändern Sie die Eigenschaft **ASM\-Listenspeicherort** \(**\/Fa**\) oder **Assemblyausgabe** \(**\/FA**\) \(**\/FAu** muss in der Eigenschaftenseite für die **Befehlszeile** im Feld **Zusätzliche Optionen** angegeben werden\).  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation*> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput*>.  Informationen zum Angeben von **\/FAu** finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Beispiel  
 Die nachfolgende Befehlszeile produziert eine kombinierte Liste mit Quellcode und Maschinencode mit dem Namen **HELLO.cod**.  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)