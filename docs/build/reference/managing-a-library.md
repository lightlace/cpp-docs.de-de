---
title: "Verwalten einer Bibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLibrarianTool.AdditionalDependencies"
  - "VC.Project.VCLibrarianTool.RemoveObjects"
  - "VC.Project.VCLibrarianTool.LibraryPaths"
  - "VC.Project.VCLibrarianTool.OutputFile"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryNames"
  - "VC.Project.VCLibrarianTool.AdditionalLibraryDirectories"
  - "VC.Project.VCLibrarianTool.ListContentsFile"
  - "VC.Project.VCLibrarianTool.ListContents"
  - "VC.Project.VCLibrarianTool.SubSystemVersion"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryName"
  - "VC.Project.VCLibrarianTool.SubSystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CONVERT (Bibliotheks-Manager-Option)"
  - "/LIBPATH (Bibliotheks-Manager-Option)"
  - "/LINK50COMPAT (Bibliotheks-Manager-Option)"
  - "/LIST (Bibliotheks-Manager-Option)"
  - "/OUT (Bibliotheks-Manager-Option)"
  - "/REMOVE (Bibliotheks-Manager-Option)"
  - "/SUBSYSTEM (Bibliotheks-Manager-Option)"
  - "CONVERT (Bibliotheks-Manager-Option)"
  - "-CONVERT (Bibliotheks-Manager-Option)"
  - "LIB [C++], Verwalten von COFF-Bibliotheken"
  - "LIBPATH (Bibliotheks-Manager-Option)"
  - "-LIBPATH (Bibliotheks-Manager-Option)"
  - "LINK50COMPAT (Bibliotheks-Manager-Option)"
  - "-LINK50COMPAT (Bibliotheks-Manager-Option)"
  - "LIST (Bibliotheks-Manager-Option)"
  - "-LIST (Bibliotheks-Manager-Option)"
  - "Objektdateien"
  - "Objektdateien, Erstellen und Ändern"
  - "OUT (Bibliotheks-Manager-Option)"
  - "-OUT (Bibliotheks-Manager-Option)"
  - "REMOVE (Bibliotheks-Manager-Option)"
  - "-REMOVE (Bibliotheks-Manager-Option)"
  - "SUBSYSTEM (Bibliotheks-Manager-Option)"
  - "-SUBSYSTEM (Bibliotheks-Manager-Option)"
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwalten einer Bibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Standardmodus von LIB wird eine Bibliothek mit COFF\-Objekten erstellt oder geändert.  LIB wird in diesem Modus ausgeführt, wenn Sie weder **\/EXTRACT** \(zum Kopieren eines Objekts in eine Datei\) noch **\/DEF** \(zum Erstellen einer Importbibliothek\) angeben.  
  
 Um eine Bibliothek aus Objekten und\/oder Bibliotheken zu erstellen, verwenden Sie die folgenden Syntax:  
  
```  
LIB [options...] files...  
```  
  
 Mit diesem Befehl wird eine Bibliothek aus einer oder mehreren Eingabedateien erstellt.  Diese Dateien \(*files*\) können COFF\-Objektdateien, 32\-Bit\-OMF\-Objektdateien oder bestehende COFF\-Bibliotheken sein.  LIB erstellt eine Bibliothek, die alle Objekte aus den angegebenen Dateien enthält.  Wenn eine Eingabedatei eine 32\-Bit\-OMF\-Objektdatei ist, konvertiert LIB sie in das COFF\-Format, bevor die Bibliothek erstellt wird.  LIB kann keine 32\-Bit\-OMF\-Objekte verarbeiten, die aus einer Bibliothek stammen, die mit der 16\-Bit\-Version von LIB erstellt wurden.  Extrahieren Sie zunächst das Objekt mit der 16\-Bit\-Version von LIB. Anschließend können Sie die extrahierte Objektdatei als Eingabe für die 32\-Bit\-Version von LIB verwenden.  
  
 LIB versieht die Ausgabedatei standardmäßig mit dem Basisnamen der ersten Objekt\- oder Bibliotheksdatei und der Dateinamenerweiterung LIB.  Die Ausgabedatei wird im aktuellen Verzeichnis gespeichert.  Ist bereits eine Datei mit demselben Namen vorhanden, wird sie durch die Ausgabedatei ersetzt.  Um eine bestehende Bibliothek zu erhalten, verwenden Sie die **\/OUT**\-Option, um einen Namen für die Ausgabedatei anzugeben.  
  
 Die folgenden Optionen beziehen sich auf das Erstellen und Ändern einer Bibliothek:  
  
 \/LIBPATH:`dir`  
 Überschreibt den Bibliothekspfad für die Umgebung.  Einzelheiten hierzu finden Sie in der Beschreibung der **LINK**\-Option [\/LIBPATH](../../build/reference/libpath-additional-libpath.md).  
  
 \/LIST  
 Zeigt Informationen über die Ausgabebibliothek in der Standardausgabe an.  Die Ausgabe kann an eine Datei umgeleitet werden.  Sie können mithilfe von \/LIST den Inhalt einer vorhandenen Bibliothek bestimmen, ohne Änderungen vorzunehmen.  
  
 **\/NAME**:*filename*  
 Gibt beim Erstellen einer wichtigen Bibliothek den Namen der DLL an, für die die Importbibliothek erstellt wird.  
  
 \/NODEFAULTLIB  
 Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen von externen Verweisen durchsucht werden.  Weitere Informationen finden Sie unter [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md).  
  
 **\/OUT**:*filename*  
 Überschreibt den Standarddateinamen für die Ausgabe.  Die Ausgabebibliothek wird standardmäßig im aktuellen Verzeichnis erstellt und mit dem Basisnamen der ersten in der Befehlszeile angegebenen Bibliothek oder Objektdatei sowie der Erweiterung LIB versehen.  
  
 **\/REMOVE**:*object*  
 Entfernt das angegebene *object* aus der Ausgabebibliothek.  LIB erstellt eine Ausgabebibliothek durch Kombinieren aller Objekte \(in Objektdateien und Bibliotheken\) und anschließendes Löschen aller angegebenen Objekte mithilfe von \/REMOVE.  
  
 \/SUBSYSTEM:{CONSOLE &#124; EFI\_APPLICATION &#124; EFI\_BOOT\_SERVICE\_DRIVER &#124; EFI\_ROM &#124; EFI\_RUNTIME\_DRIVER &#124; NATIVE &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE}\[,\#\[.\#\#\]\]  
 Teilt dem Betriebssystem mit, wie ein Programm ausgeführt werden soll, das durch Verknüpfung mit der Ausgabebibliothek erstellt wurde.  Weitere Informationen hierzu finden Sie in der Beschreibung der **LINK**\-Option [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md).  
  
 Bei in der Befehlszeile angegebenen LIB\-Optionen wird keine Groß\-\/Kleinschreibung beachtet.  
  
 Folgende Tasks der Bibliotheksverwaltung können mit LIB ausgeführt werden:  
  
-   Um einer Bibliothek Objekte hinzuzufügen, geben Sie den Dateinamen der bestehenden Bibliothek sowie die Dateinamen der neuen Objekte an.  
  
-   Um Bibliotheken miteinander zu kombinieren, geben Sie die Dateinamen der Bibliotheken an.  Sie können mit einem einzigen LIB\-Befehl sowohl Objekte hinzufügen als auch Bibliotheken kombinieren.  
  
-   Um ein Bibliothekmember durch ein neues Objekt zu ersetzen, geben Sie die Bibliothek an, die den zu ersetzenden Member enthält, sowie den Dateinamen des neuen Objekts \(bzw. der Bibliothek, die das Objekt enthält\).  Wenn ein Objekt unter demselben Namen in mehr als einer Eingabedatei vorkommt, legt LIB das zuletzt im LIB\-Befehl genannte Objekt in der Ausgabebibliothek ab.  Wenn Sie einen Bibliothekmember ersetzen, achten Sie darauf, dass Sie nach der Bibliothek, die das alte Objekt enthält, das neue Objekt oder die neue Bibliothek angeben.  
  
-   Um einen Member aus einer Bibliothek zu entfernen, verwenden Sie die **\/REMOVE**\-Option.  LIB verarbeitet unabhängig von der Reihenfolge in der Befehlszeile die **\/REMOVE\-**Angaben erst, nachdem alle Eingabeobjekte kombiniert wurden.  
  
> [!NOTE]
>  Sie können einen Member nicht gleichzeitig löschen und in eine Datei extrahieren.  Sie müssen das Memberobjekt zunächst mit der **\/EXTRACT**\-Option extrahieren und anschließend LIB erneut mit **\/REMOVE** ausführen.  Dieses Verhalten unterscheidet sich von dem der 16\-Bit\-Version von LIB \(für OMF\-Bibliotheken\), die im Lieferumfang anderer Microsoft\-Produkte enthalten ist.  
  
## Siehe auch  
 [LIB\-Referenz](../../build/reference/lib-reference.md)