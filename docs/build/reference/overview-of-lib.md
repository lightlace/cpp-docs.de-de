---
title: Übersicht über LIB
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
ms.openlocfilehash: 03209bc409453cab1769606cb972f4572d3617bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548498"
---
# <a name="overview-of-lib"></a>Übersicht über LIB

LIB erstellt Standardbibliotheken Importbibliotheken und Exportdateien können Sie mit [LINK](../../build/reference/linker-options.md) beim Erstellen eines Programms. LIB wird an einer Eingabeaufforderung ausgeführt werden.

Sie können die LIB in den folgenden Modi verwenden:

- [Erstellen oder Ändern einer COFF-Bibliothek](../../build/reference/managing-a-library.md)

- [Ein Member-Objekt in eine Datei extrahieren](../../build/reference/extracting-a-library-member.md)

- [Erstellen eine Exportdatei und eine Importbibliothek](../../build/reference/working-with-import-libraries-and-export-files.md)

Diese Modi schließen sich gegenseitig aus; Sie können nur in einem Modus zu einem Zeitpunkt LIB verwenden.

## <a name="lib-options"></a>LIB-Optionen

Die folgende Tabelle enthält die Optionen für lib.exe, die mit einem Link zu weiteren Informationen.

|Option|Beschreibung|
|-|-|
|**/DEF**|Erstellen einer Importbibliothek und einer Exportdatei.<br/><br/>Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).|
|**/ERRORREPORT**|   Senden von Informationen an Microsoft zu internen Fehlern mit lib.exe.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|
|**/EXPORT**|   Exportiert eine Funktion von Ihrem Programm an.<br/><br/>Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).|
|**/ EXTRACT**|   Erstellen einer Objektdatei (obj), die eine Kopie eines Elements aus einer bestehenden Bibliothek enthält.<br/><br/>Weitere Informationen finden Sie unter [Extrahieren eines Bibliothekmembers](../../build/reference/extracting-a-library-member.md).|
|**/INCLUDE**|   Fügt ein Symbol der Symboltabelle.<br/><br/>Weitere Informationen finden Sie unter [Erstellen einer Importbibliothek und einer Exportdatei](../../build/reference/building-an-import-library-and-export-file.md).|
|**/LIBPATH**|   Überschreibt den Bibliothekspfad der Umgebung.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/ AUFLISTEN**|   Zeigt Informationen über die Ausgabebibliothek an die Standardausgabe.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/LTCG**|   Bewirkt, dass die Bibliothek mit Link-zeitcodegenerierung erstellt werden.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|
|**/MACHINE**|   Gibt die Zielplattform für das Programm an.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|
|**/ NAME**|   Beim Erstellen einer Importbibliothek gibt den Namen der DLL für die die Importbibliothek erstellt wird.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/NODEFAULTLIB**|   Entfernt eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/NOLOGO**|   Unterdrückt die Anzeige der LIB Copyrightmeldung und der Versionsnummer, und verhindert die Anzeige von Befehlsdateien aus.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|
|**/OUT**|   Überschreibt den standardmäßigen Ausgabedateinamen.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/ ENTFERNEN**|   Lässt ein Objekt in der Ausgabebibliothek.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/SUBSYSTEM**|   Teilt dem Betriebssystem Gewusst wie: Ausführen eines Programms erstellt, indem Sie mit der Ausgabebibliothek verknüpfen.<br/><br/>Weitere Informationen finden Sie unter [Verwalten einer Bibliothek](../../build/reference/managing-a-library.md).|
|**/VERBOSE**|   Zeigt Details zu den Status der Sitzung, einschließlich Namen OBJ-Dateien hinzugefügt wird.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|
|**/WX**|   Behandeln Sie Warnungen als Fehler.<br/><br/>Weitere Informationen finden Sie unter [Ausführen von LIB](../../build/reference/running-lib.md).|

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)<br/>
[LIB-Eingabedateien](../../build/reference/lib-input-files.md)<br/>
[LIB-Ausgabedateien](../../build/reference/lib-output-files.md)<br/>
[Sonstige LIB-Ausgabe](../../build/reference/other-lib-output.md)<br/>
[Struktur einer Bibliothek](../../build/reference/structure-of-a-library.md)