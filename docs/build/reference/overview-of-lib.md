---
title: Übersicht über LIB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8fd3d370da4f841e85086e3d061508d68414e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379197"
---
# <a name="overview-of-lib"></a>Übersicht über LIB
LIB erstellt Standardbibliotheken, Importbibliotheken und Exportdateien können Sie mit [LINK](../../build/reference/linker-options.md) beim Erstellen eines Programms. LIB, die über eine Eingabeaufforderung ausgeführt wird.  
  
 Sie können LIB in den folgenden Modi:  
  
-   [Erstellen oder Ändern einer COFF-Bibliothek](../../build/reference/managing-a-library.md)  
  
-   [Extrahieren eine Member-Objekt in eine Datei](../../build/reference/extracting-a-library-member.md)  
  
-   [Erstellen eine Exportdatei und einer Importbibliothek](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 Diese Modi schließen sich gegenseitig aus; Sie können LIB jeweils nur in einem Modus verwenden.  
  
## <a name="lib-options"></a>LIB-Optionen  
 Die folgende Tabelle enthält die Optionen für lib.exe mit einem Link zu weiteren Informationen.  
  
 **/ DEF**  
 Erstellen einer Importbibliothek und einer Exportdatei an.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ERRORREPORT**  
 Informationen zu internen Fehlern mit lib.exe an Microsoft zu senden.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **/EXPORT**  
 Exportiert eine Funktion aus Ihrem Programm an.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ EXTRACT**  
 Erstellen einer Objektdatei (obj), die eine Kopie des Mitglied einer vorhandenen Bibliotheksfreigabe enthält.  
  
 Weitere Informationen finden Sie unter [Extrahieren eines Bibliothekmembers](../../build/reference/extracting-a-library-member.md).  
  
 **/ INCLUDE**  
 Der Symboltabelle wird ein Symbol hinzugefügt.  
  
 Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).  
  
 **/ LIBPATH**  
 Überschreibt den Bibliothekspfad der Umgebung.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/ LIST**  
 Zeigt Informationen zur Ausgabebibliothek an die Standardausgabe.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/LTCG**  
 Bewirkt, dass die Bibliothek mit Link-zeitcodegenerierung erstellt werden sollen.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **/ MACHINE**  
 Gibt die Zielplattform für das Programm an.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **/ NAME**  
 Beim Erstellen einer Importbibliothek gibt den Namen der DLL für die Importbibliothek erstellt wird.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/ NODEFAULTLIB**  
 Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/ NOLOGO**  
 Unterdrückt die Anzeige von der Anzahl der copyright LIB-Nachricht und Version, und verhindert die Anzeige von Befehlsdateien.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **/ OUT**  
 Überschreibt die Standard-Ausgabedatei.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/ ENTFERNEN**  
 Ein Objekt in der Ausgabebibliothek wird ausgelassen.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/SUBSYSTEM**  
 Teilt dem Betriebssystem wie Ausführen eines Programms durch Verknüpfen mit der Ausgabebibliothek erstellt.  
  
 Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).  
  
 **/ VERBOSE**  
 Zeigt Details zu den Status der Sitzung, einschließlich Namen, der die OBJ-Dateien, die hinzugefügt wird.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
 **/WX**  
 Behandeln Sie Warnungen als Fehler.  
  
 Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)   
 [LIB-Eingabedateien](../../build/reference/lib-input-files.md)   
 [LIB-Ausgabedateien](../../build/reference/lib-output-files.md)   
 [Sonstige LIB-Ausgabe](../../build/reference/other-lib-output.md)   
 [Struktur einer Bibliothek](../../build/reference/structure-of-a-library.md)