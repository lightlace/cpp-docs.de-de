---
title: Profilgesteuerte Optimierungen | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d6de281097232b1b8abc10a103af9c186e3550
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379405"
---
# <a name="profile-guided-optimizations"></a>Profilgesteuerte Optimierungen (PGO)

Mit der profilgesteuerten Optimierung können Sie eine Ausgabedatei optimieren, wobei der Optimierer Daten aus Testläufen der EXE- oder DLL-Datei verwendet. Die Daten stellen dar, wie sich das Programm in einer Produktionsumgebung wahrscheinlich verhalten wird.

Profilgesteuerte Optimierungen sind nur für X86 oder X64 systemeigene Ziele verfügbar. Profilgesteuerte Optimierungen sind nicht verfügbar für Ausgabedateien, die auf die common Language Runtime ausgeführt werden. Auch wenn Sie eine Assembly mit gemischten systemeigenen und verwalteten Code (mithilfe der **"/ CLR"** -Compileroption), können Sie Profilgesteuerte Optimierung für den systemeigenen Code verwenden. Wenn Sie versuchen, ein Projekt zu erstellen, bei dem diese Optionen in der IDE festgelegt, führt ein Buildfehler auf.

> [!NOTE]
> Informationen, die vom Test profilerstellungsausführungen gesammelt werden, überschreiben Optimierungen, die andernfalls geltende wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [/ob (Inlinefunktionserweiterung)](../../build/reference/ob-inline-function-expansion.md) und [/OS, / Ot (kompakten Code bevorzugen, schnellen Code bevorzugen)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Schritte zum Optimieren Ihrer app

Zum Verwenden der Profilgesteuerte Optimierung folgendermaßen Sie vor, um Ihre app zu optimieren:

- Kompilieren Sie eine oder mehrere Quellcodedateien mit [/GL](../../build/reference/gl-whole-program-optimization.md).

   Jedes Modul mit erstellten **/GL** untersucht werden kann, während der Testläufe Profilgesteuerte Optimierung, um das Dienstlaufzeit-Verhalten zu erfassen. Jedes Modul in einem Build für die profilgesteuerte Optimierung muss nicht kompiliert werden **/GL**. Allerdings nur die Module mit kompiliert **/GL** instrumentierte und sind später verfügbare für Profilgesteuerte Optimierungen sind.

- Verknüpfung mit [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) und [/genprofile oder/fastgenprofile](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Mit beiden **/LTCG** und **/genprofile** oder **/fastgenprofile** PGD-Datei erstellt, wenn die instrumentierte app ausgeführt wird. Nachdem die Testlaufdaten zur PGD-Datei hinzugefügt wurden, kann diese als Eingabe für den nächsten Linkschritt (Erstellen des optimierten Images) verwendet werden. Beim Angeben von **/genprofile**, Sie können optional hinzufügen eine **PGD =**_Filename_ Argument, um einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei anzugeben. Die Kombination von **/LTCG** und **/genprofile** oder **/fastgenprofile** Optionen des Linkers ersetzt die veraltete **/LTCG: PGINSTRUMENT** (Linkeroption).

- Profilieren der Anwendung

   Jedes Mal eine profilierte EXE-Sitzung endet oder eine profilierte DLL entladen wird, eine *Appname*! # .pgc-Datei erstellt. Eine PGC-Datei enthält Informationen über einen bestimmten Anwendungstestlauf. # ist eine Nummer, beginnend mit 1, der inkrementiert wird basierend auf der Anzahl anderer *Appname*! # .pgc-Dateien im Verzeichnis. Sie können eine PGC-Datei löschen, wenn der Testlauf kein zu optimierendes Szenario darstellt.

   Während eines Testlaufs können Sie erzwingen, dass Schließen der aktuell geöffneten PGC-Datei und die Erstellung einer neuen PGC-Datei mit den [Pgosweep](../../build/reference/pgosweep.md) Utility (z. B. wenn das Ende eines Testszenarios nicht zum Herunterfahren der Anwendung einhergeht).

   Ihre Anwendung kann auch direkt aufrufen eine Funktion für die profilgesteuerte Optimierung [PgoAutoSweep](pgoautosweep.md), um die Profildaten zum Zeitpunkt der Aufruf als eine PGC-Datei zu erfassen. Dadurch erhalten Sie eine präzisere Steuerung des Codes durch die erfassten Daten in die PGC-Dateien behandelt. Ein Beispiel zur Verwendung dieser Funktion finden Sie unter der [PgoAutoSweep](pgoautosweep.md) Dokumentation.

   Bei der Erstellung des instrumentierten Builds standardmäßig erfolgt die Datensammlung im Thread-sichere Modus ist schneller, aber möglicherweise nicht hundertprozentig genau. Mithilfe der **EXACT** Argument **/genprofile** oder **/fastgenprofile**, können Sie die Datensammlung in Thread-sichere Modus ist der genauere jedoch langsamer angeben. Diese Option ist auch verfügbar, wenn Sie, die als veraltet markierten festlegen [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) -Umgebungsvariablen oder der veralteten **/POGOSAFEMODE** (Linkeroption), wenn Sie Ihre instrumentierten Build erstellen.

- Verknüpfung mit **/LTCG** und **/useprofile**.

   Sowohl die **/LTCG** und [/useprofile](useprofile.md) Optionen des Linkers des optimierten Images erstellt. Bei diesem Schritt wird die PGD-Datei als Eingabe verwendet. Beim Angeben von **/useprofile**, Sie können optional Hinzufügen einer **PGD =**_Filename_ Argument, um einen nicht standardmäßigen Namen oder Speicherort für die PGD-Datei anzugeben. Sie können auch diesen Namen angeben, mit der veralteten **/PGD** (Linkeroption). Die Kombination von **/LTCG** und **/useprofile** ersetzt die veraltete **/LTCG: PGOPTIMIZE** und **/LTCG: PGUPDATE** Optionen des Linkers.

Es ist sogar möglich, die optimierte Ausgabedatei zu erstellen und später zu ermitteln, ob eine zusätzliche Profilierung zum Erstellen eines weiter optimierten Images sinnvoll wäre. Wenn das instrumentierte Image und seine PGD-Datei verfügbar sind, Sie können zusätzliche Testläufe ausführen und neu erstellt das optimierte Image mit der neueren PGD-Datei mithilfe der gleichen **/LTCG** und **/useprofile** Optionen des Linkers .

## <a name="optimizations-performed-by-pgo"></a>Vom PGO durchgeführten Optimierungen

Im Folgenden finden Sie eine Liste der profilgesteuerten Optimierungen:

- **Inlining** – z. B. vorhanden sind, die eine Funktion ein, die häufig Funktion B aufruft und Funktion B relativ klein ist, dann Profilgesteuerte Optimierungen werden Inlinefunktion B Funktion a umgewandelt.

- **Virtuelle aufrufen Spekulatives** – Wenn ein virtueller oder anderer Aufruf über einen Funktionszeiger häufig eine bestimmte Funktion zum Ziel, kann eine profilgesteuerten Optimierung einen bedingt ausgeführter direkten Aufruf der häufig als Ziel-Funktion einfügen und der direkte Aufruf als Inlinefunktion umgesetzt werden kann.

- **Registerzuweisung** – mit Profil führt zu besserer registerreservierung optimieren.

- **Basisblockoptimierung** -basisblockoptimierung ermöglicht häufig ausgeführte grundlegende Blöcke, die innerhalb eines bestimmten Rahmens in den gleichen Satz von Seiten (Lokalität) platziert werden temporär ausgeführt. Dies minimiert die Anzahl der verwendeten Seiten und damit den Arbeitsspeicherverbrauch.

- **Optimierung von Größe/Geschwindigkeit** -Funktionen, auf dem das Programm viel Zeit benötigt, können auf Geschwindigkeit optimiert werden.

- **Layout-Funktion** – Grundlage des Aufrufdiagramms und profiliert Aufrufer-/Aufgerufener-Verhalten, Funktionen, die tendenziell denselben Ausführungspfad werden im selben Abschnitt platziert.

- **Optimierung der bedingten Verzweigungen** - anhand von wertprüfungen, profilgesteuerten Optimierungen ermittelt werden, wenn ein bestimmter Wert in einer Switch-Anweisung öfter als andere Werte verwendet wird.  Dieser Wert kann dann aus der switch-Anweisung herausgezogen werden.  Dasselbe Verfahren kann bei if/else-Anweisungen verwendet werden, bei denen der Optimierer die if/else-Anweisungen so anordnen kann, dass abhängig davon, welcher Block häufiger den Wert "true" hat, entweder der if- oder der else-Block zuerst platziert wird.

- **Abtrennung von totem Code** -Code, der nicht, während der profilerstellung aufgerufen wird wird in einen speziellen Bereich, die an das Ende der Gruppe von Abschnitten angehängt wird verschoben. Damit wird dieser Abschnitt effektiv von den oft verwendeten Seiten getrennt.

- **Abtrennung von EH-Code** -Abtrennung ausgeführter EH-Code kann oft in einen separaten Abschnitt verschoben, wenn die profilgesteuerten Optimierungen ermittelt wird, dass die Ausnahmen nur unter seltenen Bedingungen eintreten.

- **Systeminterner Speicher** -die Erweiterung systeminterner Funktionen kann besser entschieden werden, wenn ermittelt werden kann, ob eine systeminterne Funktion häufig aufgerufen wird. Eine systeminterne Funktion kann auch auf Grundlage der Blockgröße von Verschiebungen oder Kopien optimiert werden.

Wenn Sie Visual Studio 2013 verwenden, können Sie die automatisierten [Profile Guided Optimization-Plug-Ins](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md) für Visual C++ in die Leistung und Diagnose-Hub, zu vereinfachen und den Optimierungsprozess in Visual Studio zu optimieren. Dieses plug-in ist nicht in höheren Versionen von Visual Studio verfügbar.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen über diese Umgebungsvariablen, Funktionen und Tools können Sie in der profilgesteuerten Optimierungen:

[Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
Diese Variablen können verwendet werden, das Laufzeitverhalten des Testszenarios angeben. Sie wurden zugunsten von neuen Optionen des Linkers als veraltet markiert; Lesen Sie diese Option, um beim Verschieben von Umgebungsvariablen für die zu den Optionen des Linkers zu unterstützen.

[PgoAutoSweep](pgoautosweep.md)<br/>
Eine Funktion können Sie Ihre app ermöglichen differenzierte PGC-Datei Data Capture-Steuerelement hinzufügen.

[pgosweep](../../build/reference/pgosweep.md)<br/>
Ein Befehlszeilenprogramm, das schreibt alle Profildaten in die PGC-Datei, schließt die PGC-Datei und öffnet eine neue PGC-Datei.

[pgomgr](../../build/reference/pgomgr.md)<br/>
Ein Befehlszeilenprogramm, das die PGD-Datei Profildaten aus einer oder mehreren PGC-Dateien hinzufügt.

[Vorgehensweise: Zusammenführen mehrerer PGO-Profile in einem einzigen Profil](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md) Beispiele für **Pgomgr** Verwendung.

## <a name="see-also"></a>Siehe auch

[C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)
