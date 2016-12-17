---
title: "/STUB (Name der MS-DOS-Stubdatei)"
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
  - "/stub"
  - "VC.Project.VCLinkerTool.DosStub"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STUB-Linkeroption"
  - "MS-DOS-Stub-Dateiname (Linkeroption)"
  - "STUB-Linkeroption"
  - "-STUB-Linkeroption"
  - "Win32 [C++], Anhängen eines MS-DOS-Stub-Programms"
  - "Windows-API [C++], Anhängen eines MS-DOS-Stub-Programms"
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /STUB (Name der MS-DOS-Stubdatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STUB:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 eine MS\-DOS\-Anwendung.  
  
## Hinweise  
 Die \/STUB\-Option fügt ein MS\-DOS\-Stub\-Programm an ein Win32\-Programm an.  
  
 Ein Stub\-Programm wird aufgerufen, wenn die Datei unter MS\-DOS ausgeführt wird.  Gewöhnlich zeigt das Programm eine entsprechende Meldung an; allerdings kann jede gültige MS\-DOS\-Anwendung ein Stub\-Programm sein.  
  
 Geben Sie in der Befehlszeile nach dem Doppelpunkt \(:\) einen *Dateinamen* für das Stub\-Programm an.  Der *Dateiname* wird vom Linker überprüft, und eine Fehlermeldung wird ausgegeben, wenn die betreffende Datei nicht ausführbar ist.  Das Programm muss eine EXE\-Datei sein; eine COM\-Datei ist als Stub\-Programm ungültig.  
  
 Wenn diese Option nicht verwendet wird, hängt der Linker ein Standard\-Stub\-Programm an, das die folgende Meldung ausgibt:  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 Beim Erstellen eines virtuellen Gerätetreibers kann vom Benutzer ein *Dateiname* angegeben werden, der eine \(in **WINNT.H** definierte\) **IMAGE\_DOS\_HEADER**\-Struktur aufweist, die im VxD anstelle des Standardheaders verwendet werden soll.  
  
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