---
title: "Profilgesteuerte Optimierungen (PGO)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Optimierung, Profilgesteuert [C++]"
  - "Profilgesteuerte Optimierungen"
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: 26
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# Profilgesteuerte Optimierungen (PGO)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit der profilgesteuerten Optimierung können Sie eine Ausgabedatei optimieren, wobei der Optimierer Daten aus Testläufen der EXE\- oder DLL\-Datei verwendet.  Die Daten stellen dar, wie sich das Programm in einer Produktionsumgebung wahrscheinlich verhalten wird.  
  
 Profilgesteuerte Optimierungen sind nur für systemeigene x86\- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Ziele verfügbar.  Profilgesteuerte Optimierungen sind nicht für Ausgabedateien verfügbar, die in der Common Language Runtime ausgeführt werden.  Auch wenn Sie eine Assembly mit einer Mischung aus systemeigenem und verwaltetem Code \(kompiliert mit **\/clr**\) erstellen, können Sie die profilgesteuerte Optimierung nicht für den systemeigenen Code verwenden.  Der Versuch, ein Projekt zu erstellen, bei dem diese Optionen in der IDE festgelegt sind, verursacht einen Buildfehler.  
  
> [!NOTE]
>  Informationen, die bei Testläufen für die Profilerstellung erfasst wurden, überschreiben Optimierungen, die sonst bei Angabe von **\/Ob**, **\/Os** oder **\/Ot** aktiv wären.  Weitere Informationen finden Sie unter [\/Ob \(Inlinefunktionserweiterung\)](../../build/reference/ob-inline-function-expansion.md) und [\/Os, \/Ot \(Kompakten Code bevorzugen, Schnellen Code bevorzugen\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  
  
 Sie können die automatisierte profilgesteuerte Optimierung für das Visual C\+\+\-Plug\-In im Hub „Leistung und Diagnose“ verwenden, um den Optimierungsprozess in Visual Studio zu vereinfachen und zu optimieren. Alternativ können Sie die Optimierungsschritte manuell in Visual Studio oder über die Befehlszeile vornehmen.  Sie sollten das Plug\-In aufgrund verwenden, da seine Verwendung einfacher ist.  Informationen über das Abrufen und Verwenden des Plug\-Ins zum Optimieren Ihrer App finden Sie unter [Plug\-In für profilgesteuerte Optimierung](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
 Sowohl das Plug\-In für die profilgesteuerte Optimierung als auch die manuelle profilgesteuerte Optimeriung befolgen diese Schritte zum Optimieren Ihrer App:  
  
-   Kompilieren von einer oder mehreren Quellcodedateien mit [\/GL](../../build/reference/gl-whole-program-optimization.md)  
  
     Jedes mit \/GL erstellte Modul kann während der profilgesteuerten Optimierungstestläufe untersucht werden, um das Laufzeitverhalten aufzuzeichnen.  Nicht jedes Modul in einem profilgesteuerten Optimierungsbuild muss mit \/GL kompiliert werden.  Jedoch werden nur die mit \/GL kompilierten Module instrumentiert und sind später für profilgesteuerte Optimierungen verfügbar.  
  
-   Linken mit [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)  
  
     \/LTCG:PGINSTRUMENT erstellt eine leere PGD\-Datei.  Nachdem die Testlaufdaten zur PGD\-Datei hinzugefügt wurden, kann diese als Eingabe für den nächsten Linkschritt \(Erstellen des optimierten Images\) verwendet werden.  Beim Angeben von \/LTCG:PGINSTRUMENT können Sie für [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md) optional einen nicht standardmäßigen Namen oder Speicherort für die PGD\-Datei festlegen.  
  
-   Profilieren der Anwendung  
  
     Jedes Mal, wenn eine profilierte EXE\-Sitzung endet oder eine profilierte DLL entladen wird, wird eine Datei *appname*\!\#.pgc erstellt.  Eine PGC\-Datei enthält Informationen über einen bestimmten Anwendungstestlauf.  \# ist eine bei 1 beginnende Nummer, die auf Basis der Anzahl anderer *appname*\!\#.pgc\-Dateien im Verzeichnis inkrementiert wird.  Sie können eine PGC\-Datei löschen, wenn der Testlauf kein zu optimierendes Szenario darstellt.  
  
     Während eines Testlaufs können Sie das Schließen der aktuell geöffneten PGC\-Datei und das Erstellen einer neuen PGC\-Datei mit dem [pgosweep](../../build/reference/pgosweep.md)\-Hilfsprogramm erzwingen \(wenn beispielsweise das Ende eines Testszenarios nicht mit dem Beenden der Anwendung einhergeht\).  
  
     Sie können die `PogoSafeMode`\-Option verwenden, wenn Sie ein Profil für die Anwendung erstellen.  Mit dieser Option können Sie festlegen, ob die Profilerstellung für die Anwendung im abgesicherten Modus oder im schnellen Modus ausgeführt werden soll.  Weitere Informationen über diese Modi finden Sie unter [PogoSafeMode](../../build/reference/pogosafemode.md).  
  
-   Linken mit \/LTGC:PGOPTIMIZE  
  
     \/LTCG:PGOPTIMIZE erstellt das optimierte Image.  Bei diesem Schritt wird die PGD\-Datei als Eingabe verwendet.  Weitere Informationen finden Sie unter [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Es ist sogar möglich, die optimierte Ausgabedatei zu erstellen und später zu ermitteln, ob eine zusätzliche Profilierung zum Erstellen eines weiter optimierten Images sinnvoll wäre.  Wenn das instrumentierte Image und seine PGD\-Datei verfügbar sind, können Sie zusätzliche Testläufe ausführen und das optimierte Image mit der neueren PGD\-Datei neu erstellen.  
  
 Im Folgenden finden Sie eine Liste der profilgesteuerten Optimierungen:  
  
-   **Inlinefunktion**: Wenn beispielsweise eine Funktion A vorhanden ist, die häufig Funktion B aufruft, und Funktion B relativ klein ist, wird bei der profilgesteuerten Optimierung Funktion B in eine Inlinefunktion von Funktion A umgewandelt.  
  
-   **Spekulatives Laden virtueller Aufrufe**: Wenn ein virtueller oder anderer Aufruf über einen Funktionszeiger häufig eine bestimmte Funktion zum Ziel hat, kann bei einer profilgesteuerten Optimierung ein bedingt ausgeführter direkter Aufruf der häufig als Ziel dienenden Funktion eingefügt und der direkte Aufruf als Inlinefunktion umgesetzt werden.  
  
-   **Registerzuweisung**: Die Optimierung mit Profildaten führt zu einer besseren Registerzuweisung.  
  
-   **Basisblockoptimierung**: Die Basisblockoptimierung ermöglicht, dass häufig ausgeführte Basisblöcke, die temporär innerhalb eines bestimmten Rahmens ausgeführt werden, in derselben Seitengruppe platziert werden \(Lokalität\).  Dies minimiert die Anzahl der verwendeten Seiten und damit den Arbeitsspeicherverbrauch.  
  
-   **Optimierung von Größe\/Geschwindigkeit**: Funktionen, für die das Programm viel Zeit benötigt, können auf Geschwindigkeit optimiert werden.  
  
-   **Funktionslayout**: Auf Grundlage des Aufrufdiagramms und des profilierten Verhaltens von aufrufender\/aufgerufener Funktion werden Funktionen, die tendenziell denselben Ausführungspfad verwenden, im selben Abschnitt platziert.  
  
-   **Optimierung der bedingten Verzweigungen**: Anhand von Wertprüfungen kann bei profilgesteuerten Optimierungen ermittelt werden, ob ein bestimmter Wert in einer switch\-Anweisung öfter als andere Werte verwendet wird.  Dieser Wert kann dann aus der switch\-Anweisung herausgezogen werden.  Dasselbe Verfahren kann bei if\/else\-Anweisungen verwendet werden, bei denen der Optimierer die if\/else\-Anweisungen so anordnen kann, dass abhängig davon, welcher Block häufiger den Wert "true" hat, entweder der if\- oder der else\-Block zuerst platziert wird.  
  
-   **Abtrennung von totem Code**: Während der Profilierung wird nicht aufgerufener Code in einen speziellen Bereich verschoben, der an das Ende der Gruppe von Abschnitten angehängt wird.  Damit wird dieser Abschnitt effektiv von den oft verwendeten Seiten getrennt.  
  
-   **Abtrennung von EH\-Code**: Bei Ausnahmen ausgeführter EH\-Code kann oft in einen separaten Abschnitt verschoben werden, wenn bei den profilgesteuerten Optimierungen ermittelt wird, dass die Ausnahmen nur unter seltenen Bedingungen eintreten.  
  
-   **Systeminterner Speicher**: Die Erweiterung systeminterner Funktionen kann besser entschieden werden, wenn feststellbar ist, ob eine systeminterne Funktion häufig aufgerufen wird.  Eine systeminterne Funktion kann auch auf Grundlage der Blockgröße von Verschiebungen oder Kopien optimiert werden.  
  
 Weitere Informationen über das Ausführen der manuellen Optimierung in der IDE oder über die Befehlszeile finden Sie unter [Exemplarische Vorgehensweise: Verwenden der profilgesteuerten Optimierung](assetId:///6e36421b-ec8c-4626-9c29-fa5ffb6f27f8).  
  
## In diesem Abschnitt  
 [Plug\-In für profilgesteuerte Optimierung](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [Tools für die profilgesteuerte Optimierung \(PGO\)](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [Gewusst wie: Zusammenführen mehrerer PGO\-Profile in einem einzigen Profil](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## Siehe auch  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)