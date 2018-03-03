---
title: Profilgesteuerte Optimierungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2d72ddda460a88830f7f7692f4c9707fa3101a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimizations"></a>Profilgesteuerte Optimierungen (PGO)
Mit der profilgesteuerten Optimierung können Sie eine Ausgabedatei optimieren, wobei der Optimierer Daten aus Testläufen der EXE- oder DLL-Datei verwendet. Die Daten stellen dar, wie sich das Programm in einer Produktionsumgebung wahrscheinlich verhalten wird.  
  
 Profilgesteuerte Optimierungen sind nur für systemeigene x86- oder [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Ziele verfügbar. Profilgesteuerte Optimierungen sind nicht für Ausgabedateien verfügbar, die in der Common Language Runtime ausgeführt werden. Auch wenn Sie eine Assembly mit gemischten systemeigenen und verwalteten Code (kompiliert mit **"/ CLR"**), können Sie die profilgesteuerte Optimierung verwenden, für den systemeigenen Code. Der Versuch, ein Projekt zu erstellen, bei dem diese Optionen in der IDE festgelegt sind, verursacht einen Buildfehler.  
  
> [!NOTE]
>  Informationen, die vom Test profilerstellungsausführungen gesammelt werden, überschreiben Optimierungen, die andernfalls geltende wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [/ob (Inlinefunktionserweiterung)](../../build/reference/ob-inline-function-expansion.md) und [/OS, / Ot (kompakten Code bevorzugen, schnellen Code bevorzugen)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  
  
 Sie können die automatisierte profilgesteuerte Optimierung für das Visual C++-Plug-In im Hub „Leistung und Diagnose“ verwenden, um den Optimierungsprozess in Visual Studio zu vereinfachen und zu optimieren. Alternativ können Sie die Optimierungsschritte manuell in Visual Studio oder über die Befehlszeile vornehmen. Sie sollten das Plug-In aufgrund verwenden, da seine Verwendung einfacher ist. Informationen zum Abrufen des Plug-Ins und zum Optimieren Ihrer app verwenden, finden Sie unter [Profile Guided Optimization-Plug-Ins](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
 Sowohl das Plug-In für die profilgesteuerte Optimierung als auch die manuelle profilgesteuerte Optimeriung befolgen diese Schritte zum Optimieren Ihrer App:  
  
-   Kompilieren Sie eine oder mehrere Quellcodedateien mit [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
     Jedes mit /GL erstellte Modul kann während der profilgesteuerten Optimierungstestläufe untersucht werden, um das Laufzeitverhalten aufzuzeichnen. Nicht jedes Modul in einem profilgesteuerten Optimierungsbuild muss mit /GL kompiliert werden. Jedoch werden nur die mit /GL kompilierten Module instrumentiert und sind später für profilgesteuerte Optimierungen verfügbar.  
  
-   Verknüpfung mit [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) und [/genprofile](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).  
  
     Mit/LTCG und/genprofile erstellt eine leere PGD-Datei. Nachdem die Testlaufdaten zur PGD-Datei hinzugefügt wurden, kann diese als Eingabe für den nächsten Linkschritt (Erstellen des optimierten Images) verwendet werden. Wenn Sie/genprofile angeben, können Sie optional hinzufügen: PGD =`filename` einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei angeben.  
  
-   Profilieren der Anwendung  
  
     Jedes Mal eine profilierte EXE-Sitzung endet oder eine profilierte DLL entladen wird, eine *Appname*! # .pgc-Datei erstellt. Eine PGC-Datei enthält Informationen über einen bestimmten Anwendungstestlauf. # ist eine Nummer, beginnend mit 1, der inkrementiert wird basierend auf der Anzahl anderer *Appname*! # .pgc-Dateien im Verzeichnis. Sie können eine PGC-Datei löschen, wenn der Testlauf kein zu optimierendes Szenario darstellt.  
  
     Während eines Testlaufs können Sie erzwingen, dass Schließen der aktuell geöffneten PGC-Datei und die Erstellung einer neuen PGC-Datei mit den [Pgosweep](../../build/reference/pgosweep.md) Utility (z. B. wenn das Ende eines Testszenarios nicht zum Herunterfahren der Anwendung einhergeht).  
  
     Sie können die `PogoSafeMode`-Option verwenden, wenn Sie ein Profil für die Anwendung erstellen. Mit dieser Option können Sie festlegen, ob die Profilerstellung für die Anwendung im abgesicherten Modus oder im schnellen Modus ausgeführt werden soll. Weitere Informationen über diese Modi finden Sie unter [PogoSafeMode](../../build/reference/pogosafemode.md).  
  
-   Verknüpfen Sie mit/LTCG und/useprofile.  
  
     Verwenden von/LTCG und/useprofile erstellt das optimierte Image. Bei diesem Schritt wird die PGD-Datei als Eingabe verwendet. Wenn Sie/useprofile angeben, können Sie optional hinzufügen: PGD =`filename` einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei angeben. Weitere Informationen finden Sie unter [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Es ist sogar möglich, die optimierte Ausgabedatei zu erstellen und später zu ermitteln, ob eine zusätzliche Profilierung zum Erstellen eines weiter optimierten Images sinnvoll wäre. Wenn das instrumentierte Image und seine PGD-Datei verfügbar sind, können Sie zusätzliche Testläufe ausführen und das optimierte Image mit der neueren PGD-Datei neu erstellen.  
  
 Im Folgenden finden Sie eine Liste der profilgesteuerten Optimierungen:  
  
-   **Inlining** – z. B. vorhanden sind, die eine Funktion ein, die häufig Funktion B aufruft und Funktion B relativ klein ist, dann Profilgesteuerte Optimierungen werden Inlinefunktion B Funktion a umgewandelt.  
  
-   **Virtuelle aufrufen Spekulatives** – Wenn ein virtueller oder anderer Aufruf über einen Funktionszeiger häufig eine bestimmte Funktion zum Ziel, kann eine profilgesteuerten Optimierung einen bedingt ausgeführter direkten Aufruf der häufig als Ziel-Funktion einfügen und der direkte Aufruf als Inlinefunktion umgesetzt werden kann.  
  
-   **Registerzuweisung** – mit Profil führt zu besserer registerreservierung optimieren.  
  
-   **Basisblockoptimierung** -basisblockoptimierung ermöglicht häufig ausgeführte grundlegende Blöcke, die innerhalb eines bestimmten Rahmens in den gleichen Satz von Seiten (Lokalität) platziert werden temporär ausgeführt. Dies minimiert die Anzahl der verwendeten Seiten und damit den Arbeitsspeicherverbrauch.  
  
-   **Optimierung von Größe/Geschwindigkeit** -Funktionen, auf dem das Programm viel Zeit benötigt, können auf Geschwindigkeit optimiert werden.  
  
-   **Layout-Funktion** – Grundlage des Aufrufdiagramms und profiliert Aufrufer-/Aufgerufener-Verhalten, Funktionen, die tendenziell denselben Ausführungspfad werden im selben Abschnitt platziert.  
  
-   **Optimierung der bedingten Verzweigungen** - anhand von wertprüfungen, profilgesteuerten Optimierungen ermittelt werden, wenn ein bestimmter Wert in einer Switch-Anweisung öfter als andere Werte verwendet wird.  Dieser Wert kann dann aus der switch-Anweisung herausgezogen werden.  Dasselbe Verfahren kann bei if/else-Anweisungen verwendet werden, bei denen der Optimierer die if/else-Anweisungen so anordnen kann, dass abhängig davon, welcher Block häufiger den Wert "true" hat, entweder der if- oder der else-Block zuerst platziert wird.  
  
-   **Abtrennung von totem Code** -Code, der nicht, während der profilerstellung aufgerufen wird wird in einen speziellen Bereich, die an das Ende der Gruppe von Abschnitten angehängt wird verschoben. Damit wird dieser Abschnitt effektiv von den oft verwendeten Seiten getrennt.  
  
-   **Abtrennung von EH-Code** -Abtrennung ausgeführter EH-Code kann oft in einen separaten Abschnitt verschoben, wenn die profilgesteuerten Optimierungen ermittelt wird, dass die Ausnahmen nur unter seltenen Bedingungen eintreten.  
  
-   **Systeminterner Speicher** -die Erweiterung systeminterner Funktionen kann besser entschieden werden, wenn ermittelt werden kann, ob eine systeminterne Funktion häufig aufgerufen wird. Eine systeminterne Funktion kann auch auf Grundlage der Blockgröße von Verschiebungen oder Kopien optimiert werden.  
  
 Weitere Informationen zum Ausführen der manuellen Optimierung in der IDE oder in der Befehlszeile können, finden Sie unter [Profile Guided Optimization-Plug-Ins](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Profilgesteuerte Optimierung-Plug-in](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [Tools für die manuelle profilgesteuerte Optimierung (PGO)](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)