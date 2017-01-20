---
title: "Linkertoolfehler LNK1104"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1104"
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datei 'dateiname' konnte nicht geöffnet werden.  
  
 Das Tool konnte die angegebene Datei nicht öffnen.  
  
 Dieser Fehler kann eine der folgenden Ursachen haben:  
  
-   Nicht genügend Speicherplatz.  
  
-   Die Datei ist nicht vorhanden.  
  
-   Wenn Bibliotheken im Eigenschaften\-Dialogfeld eines Projekts angegeben werden, sollten die Bibliotheksnamen durch Leerzeichen \(nicht durch Kommas\) getrennt werden.  
  
-   Falscher Dateiname oder Pfad.  
  
-   Ungültige Laufwerksangabe.  
  
-   Unzureichende Dateiberechtigungen.  
  
-   Der Pfad für `filename` wird auf mehr als 260 Zeichen erweitert.  
  
-   Wenn die vorhandene Datei den Namen `LNKn` hat, also einen vom Linker für eine temporäre Datei generierten Dateinamen, ist das in der Umgebungsvariablen „TMP“ angegebene Verzeichnis möglicherweise nicht vorhanden, oder es sind mehrere Verzeichnisse für die TMP\-Umgebungsvariable festgelegt. \(Es darf nur ein Verzeichnispfad für die TMP\-Umgebungsvariable festgelegt werden.\)  
  
-   Wenn die Fehlermeldung für einen Bibliotheksnamen auftritt und Sie kürzlich die MAK\-Datei von einem früheren Microsoft Visual C\+\+\-Entwicklungssystem portiert haben, ist die Bibliotheksdatei möglicherweise nicht mehr gültig. Überprüfen Sie in diesem Fall, ob die Bibliothek noch vorhanden ist.  
  
-   Möglicherweise ist die Datei in einem anderen Programm geöffnet, und der Linker kann nicht in sie schreiben.  
  
-   Falsche LIB\-Umgebungsvariable. Informationen zum Aktualisieren der LIB\-Umgebungsvariablen finden Sie unter [Eigenschaftenseite "VC\+\+\-Verzeichnisse"](../../ide/vcpp-directories-property-page.md) . Achten Sie darauf, dass hier alle benötigten Verzeichnisse mit Bibliotheken aufgeführt sind.  
  
 Der Linker verwendet im verschiedenen Fällen temporäre Dateien. Auch, wenn Sie über genügend Speicherplatz verfügen, kann eine sehr umfangreiche Verknüpfung den Adressraum ausschöpfen oder fragmentieren.  
  
 Dieser Fehler kann auf eine der folgenden Weisen behoben werden:  
  
-   Verwenden Sie [\/OPT \(Optimierungen\)](../../build/reference/opt-optimizations.md); bei der transitiven COMDAT\-Eliminierung werden alle Objektdateien mehrfach gelesen.  
  
-   Führen Sie ein Upgrade auf Windows XP aus.