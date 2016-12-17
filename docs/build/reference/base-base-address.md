---
title: "/BASE (Basisadresse)"
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
  - "/base"
  - "VC.Project.VCLinkerTool.BaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BASE (Linkeroption)"
  - "@-Symbol für Basisadresse"
  - "At-Zeichen für Basisadresse"
  - "Basisadressen [C++]"
  - "BASE (Linkeroption)"
  - "-BASE (Linkeroption)"
  - "DLLs [C++], Verknüpfen"
  - "Umgebungsvariablen [C++], LIB"
  - "Ausführbare Dateien [C++], Basisadresse"
  - "Schlüsseladressengröße"
  - "LIB-Umgebungsvariable"
  - "Programme [C++], Basisadresse"
  - "Programme [C++], Verhindern von Umsetzungen"
  - "Semikolon [C++], Spezifizierer"
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: 15
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /BASE (Basisadresse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BASE:{address[,size] | @filename,key}  
```  
  
 Die Option **\/BASE** legt eine Basisadresse für das Programm fest und überschreibt dabei die Standardadresse für eine EXE\-Datei \(0x400000\) oder eine DLL\-Datei \(0x10000000\).  Das Betriebssystem versucht zunächst, ein Programm an seine angegebene oder vorbelegte Basisadresse zu laden.  Wenn dort nicht ausreichend Speicherplatz vorhanden ist, wird das Programm vom System verschoben.  Verwenden Sie die Option [\/FIXED](../../build/reference/fixed-fixed-base-address.md), um eine Verschiebung zu verhindern.  
  
 Der Linker gibt einen Fehler aus, wenn *address* kein Vielfaches von 64 K ist.  Sie können optional eine Größe für das Programm angeben, sodass der Linker eine Warnung ausgibt, wenn das Programm diese Größe übersteigt.  
  
 In der Befehlszeile kann die Basisadresse auch noch auf andere Art festgelegt werden, indem vor dem Dateinamen \(*filename*\) das @\-Zeichen und ein Schlüssel \(key\) für die Datei angegeben wird.  Der Dateiname steht für eine Textdatei, die die Speicherplätze und Größen aller DLLs enthält, die Ihr Programm verwendet.  Der Linker sucht entweder im angegebenen Pfad oder, falls kein Pfad angegeben wurde, in den Verzeichnissen, die in der LIB\-Umgebungsvariablen angegeben sind, nach der Datei.  Jede Zeile in *filename* entspricht einer DLL und hat die folgende Syntax:  
  
```  
  
key address [size] ;comment  
```  
  
 Der Schlüssel \(`key`\) ist eine Folge alphanumerischer Zeichen ohne Berücksichtigung der Groß\-\/Kleinschreibung.  In den meisten Fällen handelt es sich hierbei um den Namen einer DLL.  Auf den Schlüssel \(`key`\) folgt in der C\-Sprache eine Basisadresse in hexadezimaler oder dezimaler Notation sowie optional eine maximale Größe \(`size`\).  Alle drei Argumente werden durch Leerzeichen oder Tabulatorzeichen voneinander getrennt.  Der Linker gibt eine Warnmeldung aus, wenn die angegebene Größe kleiner als der virtuelle Adressraum ist, den das Programm benötigt.  Ein Kommentar \(`comment`\) wird durch ein Semikolon \(;\) gekennzeichnet und kann auf derselben oder auf einer eigenen Zeile angezeigt werden.  Der Linker lässt den gesamten Text vom Semikolon bis zum Zeilenende unberücksichtigt.  Das folgende Beispiel zeigt einen Teil einer derartigen Datei:  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 Wenn die Datei mit diesen Zeilen den Namen **DLLS.txt** hat, dann werden im folgenden Befehlsbeispiel diese Informationen angewendet:  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## Hinweise  
 Sie können das Paging von Speicherseiten reduzieren und damit die Verarbeitungsgeschwindigkeit des Programms verbessern, indem Sie Basisadressen so zuordnen, dass DLLs sich im Adressraum nicht überschneiden.  
  
 Ein anderer Weg, die Basisadresse festzulegen, besteht darin, das *BASE*\-Argument in einer [NAME](../../build/reference/name-c-cpp.md)\-Anweisung oder [LIBRARY](../../build/reference/library.md)\-Anweisung zu verwenden.  Die Optionen **\/BASE** und [\/DLL](../../build/reference/dll-build-a-dll.md) sind zusammen das Äquivalent zur **LIBRARY**\-Anweisung.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Basisadresse**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)