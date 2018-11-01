---
title: Profilgesteuerte Optimierungen (PGO)
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
ms.openlocfilehash: eb23d91de210ddc9e12886924af3450ce67330d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632552"
---
# <a name="profile-guided-optimizations"></a>Profilgesteuerte Optimierungen (PGO)

Mit der profilgesteuerten Optimierung können Sie eine Ausgabedatei optimieren, wobei der Optimierer Daten aus Testläufen der EXE- oder DLL-Datei verwendet. Die Daten stellen dar, wie sich das Programm in einer Produktionsumgebung wahrscheinlich verhalten wird.

Profilgesteuerte Optimierungen sind nur für systemeigene Ziele von X86 oder X64 verfügbar. Profilgesteuerte Optimierungen sind nicht verfügbar, für die Ausgabedateien, die auf die common Language Runtime ausgeführt werden. Auch wenn Sie eine Assembly mit gemischten systemeigenen und verwalteten Code erzeugen (mithilfe der **"/ CLR"** -Compileroption), können keine Profilgesteuerte Optimierung für den systemeigenen Code. Wenn Sie versuchen, ein Projekt mit den folgenden Optionen festlegen, in der IDE zu erstellen, führt ein Buildfehler auf.

> [!NOTE]
> Informationen, die profilerstellung gesammelt werden, überschreiben Optimierungen, die andernfalls gültig wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [/ob (Inlinefunktionserweiterung)](../../build/reference/ob-inline-function-expansion.md) und [/OS, / Ot (kompakten Code bevorzugen, schnellen Code bevorzugen)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Schritte zum Optimieren Ihrer app

Um die profilgesteuerte Optimierung zu verwenden, folgendermaßen Sie vor, um Ihre app zu optimieren:

- Kompilieren Sie eine oder mehrere Quellcodedateien mit ["/ GL"](../../build/reference/gl-whole-program-optimization.md).

   Jedes Modul mit erstellten **"/ GL"** untersucht werden kann, während der profilgesteuerten Optimierungstestläufe Laufzeitverhalten zu erfassen. Jedes Modul in einem Build mit profilgesteuerter Optimierung muss nicht mit kompiliert werden **"/ GL"**. Allerdings nur die Module mit kompiliert **"/ GL"** instrumentierte und höher verfügbare ist, für die profilgesteuerte Optimierungen sind.

- Verknüpfung mit ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) und [/genprofile oder/fastgenprofile](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Mit beiden **"/ LTCG"** und **/genprofile** oder **/fastgenprofile** PGD-Datei erstellt, wenn die instrumentierte app ausgeführt wird. Nachdem die Testlaufdaten zur PGD-Datei hinzugefügt wurden, kann diese als Eingabe für den nächsten Linkschritt (Erstellen des optimierten Images) verwendet werden. Beim angeben **/genprofile**, Sie können optional hinzufügen eine **PGD =**_Dateiname_ Argument für einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei angeben. Die Kombination von **"/ LTCG"** und **/genprofile** oder **/fastgenprofile** Optionen des Linkers ersetzt die veraltete **/LTCG: PGINSTRUMENT** Linkeroption.

- Profilieren der Anwendung

   Jedes Mal eine profilierte EXE-Sitzung endet oder eine profilierte DLL entladen wird, eine *Appname*! # .pgc-Datei erstellt. Eine PGC-Datei enthält Informationen über einen bestimmten Anwendungstestlauf. # ist eine Nummer, beginnend mit 1, der um eins erhöht wird, basierend auf der Anzahl von anderen *Appname*! # .pgc-Dateien im Verzeichnis. Sie können eine PGC-Datei löschen, wenn der Testlauf kein zu optimierendes Szenario darstellt.

   Während eines Testlaufs können Sie erzwingen, dass Schließen der aktuell geöffneten PGC-Datei und das Erstellen einer neuen PGC-Datei mit den [Pgosweep](../../build/reference/pgosweep.md) -Dienstprogramms (z. B., wenn das Ende eines Testszenarios nicht mit Herunterfahren der Anwendung einhergeht).

   Ihre Anwendung kann auch direkt aufrufen eine Funktion PGO ["PgoAutoSweep"](pgoautosweep.md), um die Profildaten zum Zeitpunkt des Aufrufs als eine PGC-Datei zu erfassen. Dadurch erhalten Sie eine präzisere Kontrolle über den Code, durch die erfassten Daten in Ihren PGC-Dateien behandelt. Ein Beispiel dafür, wie Sie diese Funktion verwenden, finden Sie die ["PgoAutoSweep"](pgoautosweep.md) Dokumentation.

   Bei der Erstellung Ihres instrumentierten Builds standardmäßig erfolgt die Datensammlung im Modus "nicht threadsichere" die ist schneller, aber möglicherweise nicht hundertprozentig genau. Mithilfe der **EXACT** Argument **/genprofile** oder **/fastgenprofile**, können Sie die Datensammlung im threadsicheren Modus, handelt es sich jedoch langsamer genauer angeben. Diese Option ist auch verfügbar, wenn Sie, die als veraltet markierten festlegen [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) Umgebungsvariablen oder die veraltete **/POGOSAFEMODE** -Linkeroption, wenn Sie Ihre instrumentierten Build erstellen.

- Verknüpfung mit **"/ LTCG"** und **/USERPROFILE angegeben**.

   Sowohl die **"/ LTCG"** und [/USERPROFILE angegeben](useprofile.md) Linkeroptionen zum Erstellen des optimierten Images. Bei diesem Schritt wird die PGD-Datei als Eingabe verwendet. Beim Angeben von **/USERPROFILE angegeben**, Sie können optional hinzufügen eine **PGD =**_Filename_ Argument für einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei angeben. Sie können auch diesen Namen angeben, mit der veralteten **/PGD** -Linkeroption. Die Kombination von **"/ LTCG"** und **/USERPROFILE angegeben** ersetzt die veraltete **/LTCG: PGOPTIMIZE** und **/LTCG: PGUPDATE** Optionen des Linkers.

Es ist sogar möglich, die optimierte Ausgabedatei zu erstellen und später zu ermitteln, ob eine zusätzliche Profilierung zum Erstellen eines weiter optimierten Images sinnvoll wäre. Wenn das instrumentierte Image und seine PGD-Datei verfügbar sind, die Ihnen zusätzliche Testläufe ausführen und erstellen Sie das optimierte Image mit der neueren PGD-Datei, neu, mit der gleichen **"/ LTCG"** und **/USERPROFILE angegeben** Optionen des Linkers .

## <a name="optimizations-performed-by-pgo"></a>Vom PGO durchgeführten Optimierungen

Im Folgenden finden Sie eine Liste der profilgesteuerten Optimierungen:

- **Inlining** – beispielsweise, wenn eine Funktion ein, dass häufig B aufruft Funktion, und die Funktion B relativ klein ist und die profilgesteuerte Optimierungen Funktion B in der Funktion a werden vorhanden ist

- **Virtuelles aufrufen Spekulatives** – Wenn ein virtueller oder anderer Aufruf über einen Funktionszeiger häufig eine bestimmte Funktion ausgerichtet ist, kann eine profilgesteuerten Optimierung einen bedingt ausgeführter direkten Aufruf der Funktion häufig als Ziel einfügen und der direkte Aufruf als Inlinefunktion umgesetzt werden kann.

- **Registerzuweisung** – mit Profil führt zu besseren registerzuweisung optimieren.

- **Grundlegende Block Optimierung** -basisblockoptimierung ermöglicht, häufig ausgeführte basisblöcke, die innerhalb eines bestimmten Rahmens, der in den gleichen Satz von Seiten (Lokalität) platziert werden temporär ausgeführt. Dies minimiert die Anzahl der verwendeten Seiten und damit den Arbeitsspeicherverbrauch.

- **Optimierung von Größe/Geschwindigkeit** -Funktionen, in denen das Programm viel Zeit benötigt, können auf Geschwindigkeit optimiert werden.

- **Funktion Layout** – basierend auf das Aufrufdiagramm und Aufrufer-/Aufgerufener-Verhalten, profiliert Funktionen, die tendenziell denselben Ausführungspfad werden im selben Abschnitt platziert.

- **Optimierung der bedingten Verzweigungen** – anhand von wertprüfungen, Profilgesteuerte Optimierungen können ermitteln, indem ein bestimmter Wert in einer Switch-Anweisung öfter als andere Werte verwendet wird.  Dieser Wert kann dann aus der switch-Anweisung herausgezogen werden.  Dasselbe Verfahren kann bei if/else-Anweisungen verwendet werden, bei denen der Optimierer die if/else-Anweisungen so anordnen kann, dass abhängig davon, welcher Block häufiger den Wert "true" hat, entweder der if- oder der else-Block zuerst platziert wird.

- **Abtrennung von totem Code** -Code, der während der profilerstellung nicht aufgerufen wird, wird in einen speziellen Bereich, der an das Ende der Gruppe von Abschnitten angehängt wird verschoben. Damit wird dieser Abschnitt effektiv von den oft verwendeten Seiten getrennt.

- **Abtrennung von EH-Code** -ausgeführter EH-Code, die Abtrennung kann oft in einen separaten Abschnitt verschoben werden, wenn es sich bei profilgesteuerten Optimierungen ermittelt wird, dass die Ausnahmen nur unter seltenen Bedingungen eintreten.

- **Systeminterner Speicher** – die Erweiterung systeminterner Funktionen kann besser entschieden werden, wenn bestimmt werden kann, ob eine systeminterne Funktion häufig aufgerufen wird. Eine systeminterne Funktion kann auch auf Grundlage der Blockgröße von Verschiebungen oder Kopien optimiert werden.

Wenn Sie Visual Studio 2013 verwenden, können Sie das automatisierte [Profile Guided Optimization-Plug-Ins](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) für Visual C++ im Leistungs- und Diagnosehub zu vereinfachen und Optimieren Sie den Optimierungsprozess in Visual Studio. Dieses plug-in ist nicht verfügbar, in höheren Versionen von Visual Studio.

## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie mehr über diese Umgebungsvariablen, Funktionen und Tools können Sie in der profilgesteuerten Optimierungen:

[Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
Diese Variablen können an das Laufzeitverhalten des Testszenarios verwendet werden. Sie wurden zugunsten von neuen Optionen des Linkers als veraltet; Lesen Sie diese Option, um Sie von der Umgebungsvariablen zu den Optionen des Linkers wechseln können.

[PgoAutoSweep](pgoautosweep.md)<br/>
Eine Funktion, die Sie Ihrer app eine differenzierte PGC-Datei erfassen Datensteuerelement zu hinzufügen können.

[pgosweep](../../build/reference/pgosweep.md)<br/>
Ein Befehlszeilen-Hilfsprogramm, das alle Profildaten in die .pgc-Datei, schreibt die .pgc-Datei schließt und öffnet eine neue PGC-Datei.

[pgomgr](../../build/reference/pgomgr.md)<br/>
Ein Befehlszeilen-Hilfsprogramm, das die PGD-Datei Profildaten von einer oder mehreren PGC-Dateien hinzufügt.

[Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
Beispiele für **"pgomgr"** Nutzung.

## <a name="see-also"></a>Siehe auch

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)
