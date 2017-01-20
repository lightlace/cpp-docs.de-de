---
title: "&#220;bersicht &#252;ber LIB"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIB [C++], Modi"
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &#220;bersicht &#252;ber LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB erstellt Standardbibliotheken, Importbibliotheken und Exportdateien, die Sie mit [LINK](../../build/reference/linker-options.md) verwenden können, wenn Sie ein Programm erstellen.  LIB wird über eine Befehlszeile ausgeführt.  
  
 Sie können LIB in den folgenden Modi verwenden:  
  
-   [Erstellen oder Ändern einer COFF\-Bibliothek](../../build/reference/managing-a-library.md)  
  
-   [Extrahieren eines Memberobjekts in eine Datei](../../build/reference/extracting-a-library-member.md)  
  
-   [Erstellen einer Exportdatei und einer Importbibliothek](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Diese Modi schließen sich gegenseitig aus; Sie können LIB jeweils nur in einem Modus ausführen.  
  
## Lib\-Optionen  
 In der folgenden Tabelle werden die Optionen für lib.exe mit einem Link zu weiteren Informationen aufgelistet.  
  
 **\/DEF**  
 Erstellen einer Importbibliothek und einer Exportdatei.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/ERRORREPORT**  
 Senden von Informationen über interne Fehler mit lib.exe an Microsoft.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **\/EXPORT**  
 Exportieren einer Funktion aus dem Programm.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/EXTRACT**  
 Erstellen einer Objektdatei \(.obj\), die eine Kopie eines Members einer vorhandenen Bibliothek enthält.  
  
 Weitere Informationen finden Sie unter [Extrahieren eines Bibliothekmembers](../../build/reference/extracting-a-library-member.md).  
  
 **\/INCLUDE**  
 Fügt der Symboltabelle ein Symbol hinzu.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **\/LIBPATH**  
 Überschreibt den Bibliothekspfad für die Umgebung.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/LIST**  
 Zeigt Informationen über die Ausgabebibliothek in der Standardausgabe an.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/LTCG**  
 Bewirkt, dass die Bibliothek mit Link\-Zeitcodegenerierung generiert wird.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **\/MACHINE**  
 Gibt die Zielplattform für das Programm an.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **\/NAME**  
 Gibt beim Erstellen einer wichtigen Bibliothek den Namen der DLL an, für die die Importbibliothek erstellt wird.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/NODEFAULTLIB**  
 Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen von externen Verweisen durchsucht werden.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/NOLOGO**  
 Unterdrückt die Anzeige der Copyrightmeldung und der Versionsnummer von LIB und verhindert die Anzeige von Befehlsdateien.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **\/OUT**  
 Überschreibt den Standarddateinamen für die Ausgabe.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/REMOVE**  
 Lässt ein Objekt aus der Ausgabebibliothek aus.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/SUBSYSTEM**  
 Teilt dem Betriebssystem mit, wie ein Programm ausgeführt werden soll, das durch Verknüpfung mit der Ausgabebibliothek erstellt wurde.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **\/VERBOSE**  
 Zeigt Details über den Fortschritt der Sitzung an, einschließlich Namen der OBJ\-Dateien, die hinzugefügt werden.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **\/WX**  
 Behandelt Warnungen als Fehler.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
## Siehe auch  
 [LIB\-Referenz](../../build/reference/lib-reference.md)   
 [LIB\-Eingabedateien](../../build/reference/lib-input-files.md)   
 [LIB\-Ausgabedateien](../../build/reference/lib-output-files.md)   
 [Sonstige LIB\-Ausgabe](../../build/reference/other-lib-output.md)   
 [Struktur einer Bibliothek](../../build/reference/structure-of-a-library.md)