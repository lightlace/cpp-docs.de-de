---
title: Verwalten einer Bibliothek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
dev_langs: C++
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05ced49a960aea0b32365b80fe76095893f63d5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="managing-a-library"></a>Verwalten einer Bibliothek
Der Standardmodus für LIB ist eine Bibliothek mit COFF-Objekte zu erstellen. LIB, die in diesem Modus ausgeführt werden, wenn Sie keinen/Extract (zum Kopieren eines Objekts in eine Datei) oder/DEF (zum Erstellen einer Importbibliothek) angeben.  
  
 Verwenden Sie die folgende Syntax, um eine Bibliothek von Objekten und/oder Bibliotheken zu erstellen:  
  
```  
LIB [options...] files...  
```  
  
 Dieser Befehl erstellt eine Bibliothek aus einer oder mehreren Eingabedateien *Dateien*. Die *Dateien* COFF-Objektdateien, 32-Bit-OMF-Objektdateien oder bestehende COFF-Bibliotheken werden können. LIB erstellt eine Bibliothek, die alle Objekte in den angegebenen Dateien enthält. Wenn eine Eingabedatei eine 32-Bit-OMF-Objektdatei ist, konvertiert LIB in COFF vor dem Erstellen der Bibliotheks. LIB kann kein 32-Bit-OMF-Objekt akzeptieren, die in einer Bibliothek, die von der 16-Bit-Version von LIB erstellt wird. Zum Extrahieren des Objekts, müssen Sie zuerst die 16-Bit-Bibliothek verwenden. Anschließend können Sie die extrahierte Objektdatei als Eingabe für die 32-Bit-Bibliothek.  
  
 Standardmäßig Namen LIB Ausgabedatei mit den Basisnamen der ersten Objekt- oder Bibliotheksdatei-Datei und die Erweiterung. Lib. Die Ausgabedatei wird im aktuellen Verzeichnis abgelegt. Wenn eine Datei mit dem gleichen Namen bereits vorhanden ist, ersetzt die Ausgabedatei die vorhandene Datei an. Um einer vorhandenen Bibliotheksfreigabe beizubehalten, verwenden Sie die Out-Option einen Namen für die Ausgabedatei an.  
  
 Die folgenden Optionen gelten für erstellen und Ändern einer Bibliothek:  
  
 / LIBPATH:`dir`  
 Überschreibt den Bibliothekspfad der Umgebung. Weitere Informationen finden Sie unter der Beschreibung der Verknüpfung [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option.  
  
 / LIST  
 Zeigt Informationen zur Ausgabebibliothek an die Standardausgabe. Die Ausgabe kann in eine Datei umgeleitet werden. Sie können/List verwenden, um den Inhalt einer vorhandenen Bibliotheksfreigabe zu ermitteln, ohne Sie zu ändern.  
  
 / NAME: *Dateiname*  
 Beim Erstellen einer Importbibliothek gibt den Namen der DLL für die Importbibliothek erstellt wird.  
  
 /NODEFAULTLIB  
 Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht. Finden Sie unter [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) für Weitere Informationen.  
  
 / OUT: *Dateiname*  
 Überschreibt die Standard-Ausgabedatei. Standardmäßig wird der Ausgabebibliothek im aktuellen Verzeichnis mit den Basisnamen der ersten Bibliothek oder Objektdatei Datei auf der Befehlszeile und die Erweiterung erstellt. Lib.  
  
 / Entfernen: *Objekt*  
 Entfernt das angegebene *Objekt* in der Ausgabebibliothek. LIB erstellt eine Ausgabebibliothek durch Kombinieren aller Objekte (entweder in Objektdateien oder Bibliotheken) und löschen alle Objekte, die mit/Remove angegeben.  
  
 / SUBSYSTEM: {KONSOLE &#124; EFI_APPLICATIONS &#124; EFI_BOOT_SERVICE_DRIVER &#124; EFI_ROM &#124; EIN EFI_RUNTIME_DRIVER &#124; SYSTEMEIGENE &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE} [, #[. ##]]  
 Teilt dem Betriebssystem wie Ausführen eines Programms durch Verknüpfen mit der Ausgabebibliothek erstellt. Weitere Informationen finden Sie unter der Beschreibung der Verknüpfung [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) Option.  
  
 In der Befehlszeile angegebene LIB-Optionen sind nicht in der Groß-/Kleinschreibung beachtet.  
  
 LIB können Sie die folgenden Bibliothek-Management-Aufgaben ausführen:  
  
-   Hinzufügen von Objekten in einer Bibliothek, geben Sie den Dateinamen für die vorhandenen Bibliotheksfreigabe und den Dateinamen für die neuen Objekte.  
  
-   Bibliotheken zu kombinieren, geben Sie die Bibliothek-Dateinamen ein. Sie können Objekte hinzufügen und Kombinieren von Bibliotheken mit einem einzigen LIB-Befehl.  
  
-   Geben Sie zum Ersetzen eines Bibliothekmembers durch ein neues Objekt für die Bibliothek, die die Member-Objekt ersetzt werden und den Dateinamen für das neue Objekt (oder die Bibliothek, die es enthält). Wenn ein Objekt mit demselben Namen in mehr als eine Eingabedatei vorhanden ist, setzt LIB das letzte Objekt, das in der LIB-Befehl angegeben werden, in der Ausgabebibliothek an. Wenn Sie ein Bibliothekmembers ersetzen, achten Sie darauf, dass Sie das neue Objekt oder die Bibliothek nach der Bibliothek angeben, die alten Objekts enthält.  
  
-   Um ein Element aus einer Bibliothek löschen, verwenden Sie die Option/Remove. LIB verarbeitet des/Remove nach dem kombinieren aller Objekte Eingabe-, unabhängig von der Reihenfolge.  
  
> [!NOTE]
>  Sie können nicht sowohl ein Element löschen, und extrahieren Sie es in eine Datei im gleichen Schritt. Sie müssen zuerst die mit/Extract Member extrahieren und anschließend LIB erneut mit/Remove ausführen. Dieses Verhalten unterscheidet sich von dem die 16-Bit-lib (für OMF-Bibliotheken) in anderen Produkten von Microsoft bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)