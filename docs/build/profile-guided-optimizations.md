---
title: Profilgesteuerte Optimierungen
ms.date: 04/23/2019
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
ms.openlocfilehash: 46619e77861b6a3a78d74ce6c6d9173a3a5f270f
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857328"
---
# <a name="profile-guided-optimizations"></a>Profilgesteuerte Optimierungen

Profilgesteuerte Optimierung (PGO) können Sie eine gesamte ausführbare Datei optimieren, bei denen der Optimierer Daten aus Testläufen der .exe oder .dll-Datei verwendet. Die Daten darstellt, die wahrscheinliche Leistung des Programms in einer produktionsumgebung.

Profilgesteuerte Optimierungen sind nur für systemeigene Ziele von X86 oder X64 verfügbar. Profilgesteuerte Optimierungen nicht verfügbar für ausführbare Dateien, die auf die common Language Runtime ausgeführt. Auch wenn Sie eine Assembly mit gemischten systemeigenen und verwalteten Code erzeugen (mithilfe der **"/ CLR"** -Compileroption), können keine Profilgesteuerte Optimierung für den systemeigenen Code. Wenn Sie versuchen, ein Projekt mit den folgenden Optionen festlegen, in der IDE zu erstellen, führt ein Buildfehler auf.

> [!NOTE]
> Informationen, die profilerstellung gesammelt werden, überschreiben Optimierungen, die andernfalls gültig wäre, wenn Sie angeben, **tatsächlich**, **/OS**, oder **/Ot**. Weitere Informationen finden Sie unter [/ob (Inlinefunktionserweiterung)](reference/ob-inline-function-expansion.md) und [/OS, / Ot (kompakten Code bevorzugen, schnellen Code bevorzugen)](reference/os-ot-favor-small-code-favor-fast-code.md).

## <a name="steps-to-optimize-your-app"></a>Schritte zum Optimieren Ihrer app

Um die profilgesteuerte Optimierung zu verwenden, folgendermaßen Sie vor, um Ihre app zu optimieren:

- Kompilieren Sie eine oder mehrere Quellcodedateien mit ["/ GL"](reference/gl-whole-program-optimization.md).

   Jedes Modul mit erstellten **"/ GL"** untersucht werden kann, während der profilgesteuerten Optimierungstestläufe Laufzeitverhalten zu erfassen. Jedes Modul in einem Build mit profilgesteuerter Optimierung nicht für die Kompilierung mit **"/ GL"**. Allerdings nur die Module mit kompiliert **"/ GL"** instrumentierte und höher verfügbare ist, für die profilgesteuerte Optimierungen sind.

- Verknüpfung mit ["/ LTCG"](reference/ltcg-link-time-code-generation.md) und [/genprofile oder/fastgenprofile](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).

   Mit beiden **"/ LTCG"** und **/genprofile** oder **/fastgenprofile** erstellt eine `.pgd` -Datei, wenn die instrumentierte app ausgeführt wird. Nach dem Testlauf Daten hinzugefügt werden die `.pgd` -Datei, sie können als Eingabe für den nächsten Linkschritt (Erstellen des optimierten Images) verwendet werden. Beim angeben **/genprofile**, Sie können optional hinzufügen eine **PGD =**_Dateiname_ Argument an einen nicht standardmäßigen Namen oder Speicherort für die `.pgd` Datei. Die Kombination von **"/ LTCG"** und **/genprofile** oder **/fastgenprofile** Optionen des Linkers ersetzt die veraltete **/LTCG: PGINSTRUMENT** Linkeroption.

- Profilieren der Anwendung

   Jedes Mal eine profilierte EXE-Sitzung endet, oder eine profilierte DLL entladen wird, eine `appname!N.pgc` Datei erstellt wird. Ein `.pgc` Datei enthält Informationen zu einem bestimmten Anwendungstestlauf. *Appname* ist der Name der app, und *N* basiert eine Zahl ab 1 an, der um eins erhöht wird, auf die Anzahl der anderen `appname!N.pgc` Dateien im Verzeichnis. Sie können Löschen einer `.pgc` Datei, wenn der Testlauf ein Szenario darstellen nicht, die Sie optimieren möchten.

   Während eines Testlaufs können Sie erzwingen, der aktuell geöffneten Abschlusses `.pgc` -Datei und die Erstellung eines neuen `.pgc` -Datei mit der [Pgosweep](pgosweep.md) (z. B., wenn das Ende eines Testszenarios mit Anwendung übereinstimmen, nicht-Hilfsprogramm Herunterfahren).

   Ihre Anwendung kann auch direkt aufrufen eine Funktion PGO ["PgoAutoSweep"](pgoautosweep.md), um die Profildaten zum Zeitpunkt des Aufrufs als Erfassen einer `.pgc` Datei. Sie können Ihnen eine präzisere Kontrolle über den Code behandelt, die von den erfassten Daten in Ihre `.pgc` Dateien. Ein Beispiel dafür, wie Sie diese Funktion verwenden, finden Sie die ["PgoAutoSweep"](pgoautosweep.md) Dokumentation.

   Bei der Erstellung Ihres instrumentierten Builds standardmäßig erfolgt die Datensammlung im Modus "nicht threadsichere" die ist schneller, aber unpräzise. Mithilfe der **EXACT** Argument **/genprofile** oder **/fastgenprofile**, können Sie die Datensammlung angeben, im threadsicheren Modus, die eine genauere ist, aber langsamer. Diese Option ist auch verfügbar, wenn Sie, die als veraltet markierten festlegen [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md#pogosafemode) Umgebungsvariablen oder die veraltete **/POGOSAFEMODE** -Linkeroption, wenn Sie Ihre instrumentierten Build erstellen.

- Verknüpfung mit **"/ LTCG"** und **/USERPROFILE angegeben**.

   Sowohl die **"/ LTCG"** und [/USERPROFILE angegeben](reference/useprofile.md) Linkeroptionen zum Erstellen des optimierten Images. Dieser Schritt nimmt als Eingabe die `.pgd` Datei. Beim Angeben von **/USERPROFILE angegeben**, Sie können optional hinzufügen eine **PGD =**_Filename_ Argument an einen nicht standardmäßigen Namen oder Speicherort für die `.pgd` Datei. Sie können auch diesen Namen angeben, mit der veralteten **/PGD** -Linkeroption. Die Kombination von **"/ LTCG"** und **/USERPROFILE angegeben** ersetzt die veraltete **/LTCG: PGOPTIMIZE** und **/LTCG: PGUPDATE** Optionen des Linkers.

Es ist auch möglich, die optimierte ausführbare Datei zu erstellen und zu einem späteren Zeitpunkt feststellen, dass zusätzliche Profilierung zum Erstellen eines weiter optimierten Images sinnvoll wäre. Wenn das instrumentierte Image und dessen `.pgd` Datei stehen zur Verfügung, die Ihnen zusätzliche Testläufe ausführen und Neuerstellen des optimierten Images mit neueren `.pgd` -Datei mit der gleichen **"/ LTCG"** und   **/USERPROFILE angegeben** Optionen des Linkers.

## <a name="optimizations-performed-by-pgo"></a>Vom PGO durchgeführten Optimierungen

Die profilgesteuerte Optimierungen sind diese Prüfungen und Verbesserungen:

- **Inlining** – beispielsweise, wenn eine Funktion A häufig Funktion B aufruft und Funktion B relativ klein, und klicken Sie dann mit profilgesteuerter Optimierung Funktion B Funktion a umgewandelt.

- **Virtuelles aufrufen Spekulatives** – Wenn ein virtueller oder anderer Aufruf über einen Funktionszeiger häufig eine bestimmte Funktion ausgerichtet ist, kann eine Profilgesteuerte Optimierung einen bedingt ausgeführten direkten Aufruf der häufig gezielte-Funktion, einfügen und der direkte Aufruf kann inline gesetzt werden.

- **Registerzuweisung** -Optimierung, die basierend auf dem Profil führt zu besseren registerzuweisung.

- **Grundlegende Block Optimierung** -basisblockoptimierung ermöglicht, häufig ausgeführte basisblöcke, die innerhalb eines bestimmten Rahmens, der in den gleichen Satz von Seiten (Lokalität) platziert werden temporär ausgeführt. Sie minimiert die Anzahl der Seiten, die verwendet wird, die wodurch Speicher-Overhead reduziert wird.

- **Optimierung von Größe/Geschwindigkeit** -Funktionen, in denen das Programm die Ausführungszeit benötigt, können auf Geschwindigkeit optimiert werden.

- **Funktion Layout** – basierend auf das Aufrufdiagramm und Aufrufer-/Aufgerufener-Verhalten, profiliert Funktionen, die tendenziell denselben Ausführungspfad werden im selben Abschnitt platziert.

- **Optimierung der bedingten Verzweigungen** – anhand von wertprüfungen, Profilgesteuerte Optimierungen können ermitteln, indem ein bestimmter Wert in einer Switch-Anweisung öfter als andere Werte verwendet wird.  Dieser Wert kann dann aus der switch-Anweisung herausgezogen werden.  Das gleiche erreichen Sie mit `if`... `else` Anweisungen, in denen der Optimierer sortieren kann, die `if`... `else` so, dass entweder die `if` oder `else` Block zuerst platziert wird, je nachdem welcher Block geht häufig "true".

- **Abtrennung von totem Code** -Code, der während der profilerstellung aufgerufen ist nicht in einen speziellen Bereich, der an das Ende der Gruppe von Abschnitten angehängt wird verschoben. Es bleibt in diesem Abschnitt aus der häufig verwendeten Seiten.

- **Abtrennung von EH-Code** -da ausgeführter EH-Code nur außergewöhnlich ausgeführt wird, wird häufig in einen separaten Abschnitt verschoben werden. Es wird verschoben, wenn es sich bei profilgesteuerten Optimierungen ermittelt wird, dass die Ausnahmen nur unter seltenen Bedingungen eintreten.

- **Systeminterner Speicher** –, ob eine systeminterne Funktion oder nicht erweitern hängt gibt an, ob es häufig aufgerufen wird. Eine systeminterne Funktion kann auch auf Grundlage der Blockgröße von Verschiebungen oder Kopien optimiert werden.

## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie mehr über diese Umgebungsvariablen, Funktionen und Tools können Sie in der profilgesteuerten Optimierungen:

[Umgebungsvariablen für Profilgesteuerte Optimierungen](environment-variables-for-profile-guided-optimizations.md)<br/>
Diese Variablen wurden verwendet, um das Laufzeitverhalten des Testszenarios zu anzugeben. Sie sind jetzt als veraltet markiert und durch neue Linkeroptionen ersetzt. In diesem Dokument erfahren Sie, wie Sie aus den Umgebungsvariablen in den Optionen des Linkers zu verschieben.

[PgoAutoSweep](pgoautosweep.md)<br/>
Eine Funktion, die Sie hinzufügen können, zu Ihrer app, geben Sie eine präzise `.pgc` Datei Data capture-Steuerelement.

[pgosweep](pgosweep.md)<br/>
Ein Befehlszeilen-Hilfsprogramm, das alle Profildaten, schreibt die `.pgc` -Datei, schließt die `.pgc` Datei, und öffnet einen neuen `.pgc` Datei.

[pgomgr](pgomgr.md)<br/>
Ein Befehlszeilen-Hilfsprogramm, mit dem Hinzufügen von Profildaten von einer oder mehreren `.pgc` von Dateien in die `.pgd` Datei.

[Vorgehensweise: Zusammenführen Sie mehrerer PGO-Profile in einem einzigen Profil](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
Beispiele für **"pgomgr"** Nutzung.

## <a name="see-also"></a>Siehe auch

[Zusätzliche MSVC-Buildtools](reference/c-cpp-build-tools.md)
