---
title: "/CLRIMAGETYPE (Angeben des CLR-Bildtyps) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRIMAGETYPE"
  - "VC.Project.VCLinkerTool.CLRImageType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRIMAGETYPE (Linkeroption)"
  - "-CLRIMAGETYPE (Linkeroption)"
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRIMAGETYPE (Angeben des CLR-Bildtyps)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## Hinweise  
 Der Linker akzeptiert systemeigene Objekte und auch MSIL\-Objekte, die mit [\/clr](../../build/reference/clr-common-language-runtime-compilation.md), \/clr:pure oder \/clr:safe kompiliert werden.  Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule.  Wenn Sie beispielsweise sowohl ein überprüfbares als auch ein reines \(safe und pure\) Modul an den Linker übergeben, ist die Ausgabedatei rein \(pure\).  Wenn Sie ein systemeigenes Image und ein Image im gemischten Modus \(mit **\/clr** kompiliert\) übergeben, ist das resultierende Image ein Image im gemischten Modus.  
  
 Mit \/CLRIMAGETYPE können Sie eine niedrige Überprüfbarkeitsstufe angeben, wenn dies erforderlich ist.  
  
 In .NET 4.5 unterstützt \/CLRIMAGETYPE eine SAFE32BITPREFERRED\-Option.  Damit werden im PE\-Header des Images Kennzeichen gesetzt, die darauf hinweisen, dass MSIL\-Objekte überprüfbar sind und auf allen Plattformen ausgeführt werden können, wobei jedoch 32\-Bit\-Ausführungsumgebungen bevorzugt werden.  Mit dieser Option kann eine App auf ARM\-Plattformen ausgeführt werden. Sie gibt auch an, dass sie unter WOW64 auf 64\-Bit\-Betriebssystemen anstatt in der 64\-Bit\-Ausführungsumgebung ausgeführt werden soll.  
  
 Wenn eine mit **\/clr** oder **\/clr:pure** kompilierte EXE\-Datei unter einem 64\-Bit\-Betriebssystem ausgeführt wird, wird die Anwendung unter WOW64 ausgeführt, womit eine 32\-Bit\-Anwendung unter einem 64\-Bit\-Betriebssystem ausgeführt werden kann.  Standardmäßig wird eine EXE\-Datei, die mit **\/clr:safe** kompiliert wurde, unter der unter 64\-Bit\-Unterstützung des Betriebssystems ausgeführt.  Es ist jedoch möglich, dass eine 32\-Bit\-Komponente in die überprüfbare Anwendung geladen wird.  In diesem Fall schlägt die Ausführung des mit 64\-Bit\-Unterstützung ausgeführten überprüfbaren Images beim Laden der 32\-Bit\-Anwendung fehl.  Damit ein überprüfbares Image weiterhin ausgeführt werden kann, wenn eine 32\-Bit\-Komponente auf einem 64\-Bit\-Betriebssystem geladen wird, verwenden Sie die Option \/CLRIMAGETYPE:SAFE32BITPREFERRED.  Wenn der Code nicht auf ARM\-Plattformen ausgeführt werden muss, können Sie die Option \/CLRIMAGETYPE:PURE angeben, um die Metadaten \(.corflags\) zu ändern, die markieren, dass er unter WOW64 ausgeführt werden soll \(wodurch ein eigenes Eingabezeichen ersetzt wird\):  
  
 **cl \/clr:safe t.cpp \/link \/clrimagetype:pure \/entry:?main@@$$HYMHXZ \/subsystem:console**  
  
 Weitere Informationen zum Bestimmen des CLR\-Imagetyps einer Datei finden Sie unter [\/CLRHEADER](../../build/reference/clrheader.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Erweitert** aus.  
  
5.  Ändern Sie die Eigenschaft **CLR\-Imagetyp**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)