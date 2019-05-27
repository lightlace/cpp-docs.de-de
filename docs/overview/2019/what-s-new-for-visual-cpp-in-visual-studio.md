---
title: Neuerungen bei C++ in Visual Studio 2019
ms.date: 05/13/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 19eaa9d4ed1cf12e721825f998fa674363eda488
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934138"
---
# <a name="whats-new-for-c-in-visual-studio-2019"></a>Neuerungen bei C++ in Visual Studio 2019

Visual Studio 2019 enthält viele Updates und Fixes für die C++-Umgebung von Microsoft. Es wurden zahlreiche Fehler und Probleme mit dem Compiler sowie mit Tools behoben. Viele Probleme wurden von Kunden über die Optionen [Problem melden](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) und [Vorschlag senden](https://developercommunity.visualstudio.com/spaces/62/index.html) unter **Feedback senden** übermittelt. Vielen Dank für das Melden von Fehlern! Weitere Informationen zu Neuerungen in Visual Studio finden Sie unter [Neuerungen in Visual Studio](/visualstudio/ide/whats-new-visual-studio-2019).

## <a name="c-compiler"></a>C++-Compiler

- Verbesserte Unterstützung für C++17-Features und Korrekturen der Genauigkeit sowie experimentelle Unterstützung für C++20-Features wie Module und Coroutinen. Ausführliche Informationen finden Sie unter [C++ Conformance Improvements in Visual Studio 2019 (Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual Studio 2019)](../cpp-conformance-improvements.md).

- Die Option `/std:c++latest` schließt nun C++20-Features ein, deren Entwicklung möglicherweise noch nicht abgeschlossen ist. Hierzu gehört beispielsweise die Unterstützung des C++20-Operators \<=> („Spaceship“) für Dreifachvergleiche.

- Die C++-Compileroption `/Gm` ist nun veraltet. Es empfiehlt sich, die `/Gm`-Option in Buildskripts zu deaktivieren, wenn sie explizit festgelegt wurde. Sie können die Warnung für die veraltete Option allerdings auch für `/Gm` ignorieren, da sie bei Verwendung der Einstellung „Warnungen als Fehler behandeln“ (`/WX`) nicht als Fehler behandelt wird.

- Da für MSVC mit der Implementierung der Features aus dem C++20-Standardentwurf unter dem Flag `/std:c++latest` begonnen wurde, ist `/std:c++latest` jetzt mit `/clr` (alle Arten), `/ZW` und `/Gm` inkompatibel. Verwenden Sie in Visual Studio 2019 den Modus `/std:c++17` oder `/std:c++14` beim Kompilieren mit `/clr`, `/ZW` oder `/Gm` (siehe vorheriger Aufzählungspunkt).

- Vorkompilierte Header werden nicht mehr standardmäßig für C++-Konsolen- und -Desktop-Apps generiert.

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegenerierung, Sicherheit, Diagnosen und Versionsverwaltung

Verbesserte Analysen mit `/Qspectre` unterstützen die Entschärfung der Spectre-Variante 1 (CVE-2017-5753). Weitere Informationen finden Sie unter [Spectre Mitigations in MSVC (Spectre-Entschärfungen in MSVC)](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>Verbesserungen der C++-Standardbibliothek

- Implementierung von zusätzlichen C++17- und C++20-Bibliotheksfeatures und Korrekturen der Genauigkeit. Ausführliche Informationen finden Sie unter [C++ Conformance Improvements in Visual Studio 2019 (Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual Studio 2019)](../cpp-conformance-improvements.md).

- Das Clang-Format wurde zur besseren Lesbarkeit auf die Header der C++-Standardbibliothek angewendet.

- Da Visual Studio jetzt „Nur eigenen Code“ für C++ unterstützt, muss die Standardbibliothek keine benutzerdefinierten Komponenten für `std::function` und `std::visit` mehr bereitstellen, um den gleichen Effekt zu erzielen. Die Entfernung dieser Komponenten hat im Allgemeinen keine für Benutzer sichtbare Auswirkung, mit der Ausnahme, dass der Compiler keine Diagnose zum Angeben von Problemen in Zeile 15732480 oder 16707566 von \<type_traits> oder \<variant> mehr durchführt.

## <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Verbesserungen in Bezug auf Leistung/Durchsatz im Compiler und in der Standardbibliothek

- Der Durchsatz für Builds wurde verbessert. Zu den Optimierungen gehören unter anderem der Umgang des Linkers mit E/A-Vorgängen für Dateien und die Linkzeit beim Zusammenführen und Erstellen von PDB-Typen.

- Die OpenMP-SIMD-Vektorisierung wird nun grundlegend unterstützt. Sie können sie mit dem neuen Compilerschalter `-openmp:experimental` aktivieren. Wenn diese Option festgelegt ist, werden Schleifen mit der Anmerkung `#pragma omp simd` möglicherweise vektorisiert. Die Vektorisierung wird allerdings nicht garantiert. Für Schleifen, die mit einer Anmerkung versehen sind, aber nicht vektorisiert werden, wird eine Warnung ausgegeben. SIMD-Klauseln werden nicht unterstützt und ignoriert. Dabei wird eine Warnung angezeigt.

- Die neue Inlining-Befehlszeilenoption `-Ob3` wurde hinzugefügt. Diese führt im Vergleich zur `-Ob2`-Version mehr Inliningvorgänge aus. `-O2` (Binärdateioptimierung für höhere Geschwindigkeit) impliziert weiterhin standardmäßig `-Ob2`. Wenn Sie feststellen, dass der Compiler nicht genug Inliningvorgänge ausführt, sollten Sie `-O2 -Ob3` verwenden.

- Intrinsische Funktionen der Short Vector Math Library (SVML) werden nun unterstützt. Dadurch werden die manuelle Vektorisierung von Schleifen mit Aufrufen für mathematische Bibliotheksfunktionen und bestimmte andere Operationen wie Ganzzahldivisionen ermöglicht. Diese Funktionen berechnen die Entsprechungen von 128-, 256- oder 512-Bit-Vektoren. Definitionen der unterstützten Funktionen finden Sie im [Intel Intrinsics Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML).

- Neue und verbesserte Optimierungen:

  - Auswertung von Ausdrücken, die zur Kompilierzeit in Konstanten umgewandelt werden können (Constant Folding), und arithmetische Vereinfachungen für Ausdrücke mit intrinsischen SIMD-Vektorfunktionen für Float- und Integerformen

  - Leistungsfähigere Analyse zum Extrahieren von Informationen aus der Ablaufsteuerung (if/else/switch-Anweisungen), um Zweige zu entfernen, für die feststeht, dass sie immer TRUE oder FALSE sind

  - Verbesserte memset-Auflösung zur Verwendung von SSE2-Vektoranweisungen

  - Verbessertes Entfernen von nutzlosen struct/class-Kopien, insbesondere für C++-Programme, in denen Übergaben nach Wert erfolgen

  - Verbesserte Optimierung von Code mithilfe von `memmove`, z. B. im Fall von `std::copy` oder bei der Erstellung von `std::vector`- und `std::string`-Objekten

- Das physische Design der Standardbibliothek wurde optimiert, um das Kompilieren bestimmter Teile der Standardbibliothek zu vermeiden, die nicht über #include-Anweisungen eingebunden werden. Dadurch wird die Buildzeit für eine leere Datei halbiert, die nur \<vector> einschließt. Das Ergebnis dieser Änderung ist, dass Sie ggf. #include-Anweisungen für Header hinzufügen müssen, die zuvor indirekt eingebunden waren. Beispielsweise muss Code, für den `std::out_of_range` verwendet wird, jetzt ggf. über „#include \<stdexcept>“ verfügen. Code, für den ein Operator zum Einfügen eines Datenstroms verwendet wird, muss jetzt ggf. über „#include \<ostream>“ verfügen. Der Vorteil besteht darin, dass nur für Übersetzungseinheiten, in denen tatsächlich \<stdexcept>- oder \<ostream>-Komponenten verwendet werden, der Durchsatzaufwand für die Kompilierung anfällt.

- `if constexpr` wurde in der Standardbibliothek an mehr Stellen angewendet, um für Kopiervorgänge einen besseren Durchsatz und eine geringere Codegröße zu erzielen, sowie in Permutationen wie Umkehrung und Drehung und in der Bibliothek mit den parallelen Algorithmen. 

- In der Standardbibliothek wird intern jetzt `if constexpr` verwendet, um die Kompilierzeiten zu reduzieren (auch im C ++14-Modus).

- Bei der Erkennung von dynamischen Verknüpfungen zur Laufzeit für die Bibliothek mit den parallelen Algorithmen wird nicht mehr eine gesamte Seite genutzt, um das Funktionszeigerarray zu speichern. Die Kennzeichnung dieses Speichers als schreibgeschützt wurde als nicht mehr relevant für die Sicherheit angesehen.

- Der Konstruktor `std::thread` wartet nicht mehr darauf, dass der Thread startet, und fügt zwischen der zugrunde liegenden C-Bibliothek `_beginthreadex` und dem angegebenen aufrufbaren Objekt nicht mehr so viele Funktionsaufrufe ein. Bisher wurden von `std::thread` sechs Funktionen zwischen `_beginthreadex` und dem angegebenen aufrufbaren Objekt eingefügt. Diese Zahl wurde auf nur noch drei reduziert (zwei davon sind lediglich `std::invoke`). Darüber hinaus wird hiermit ein rätselhafter Zeitsteuerungsfehler behoben, bei dem der Konstruktor von `std::thread` hängt, wenn die Systemuhr genau während der Erstellung eines `std::thread`-Elements geändert wird.

- Es wurde ein Leistungsverlust in `std::hash` behoben, der sich aus der Implementierung von `std::hash<std::filesystem::path>` ergeben hat.

- An mehreren Stellen der Standardbibliothek werden anstelle von catch-Blöcken jetzt Destruktoren verwendet, um Korrektheit zu erzielen. Dies führt zu einer besseren Interaktion mit dem Debugger. Ausnahmen, die über die Standardbibliothek an den betroffenen Orten auftreten, werden jetzt so angezeigt, dass sie am ursprünglichen Auslösungsort ausgelöst wurden (anstatt durch unseren Rethrow-Vorgang). Nicht alle catch-Blöcke der Standardbibliothek wurden beseitigt. Wir rechnen damit, dass in den nachfolgenden Versionen von MSVC die Anzahl von catch-Blöcken weiter reduziert wird.

- Suboptimale Codegenerierung in `std::bitset` durch eine bedingte Auslösung in einer noexcept-Funktion wurde behoben, indem der Auslösepfad ausgeklammert wurde.

- Für die `std::list`- und `std::unordered_*`-Familie werden Iteratoren ohne Debugging intern an mehr Stellen verwendet.

- Mehrere `std::list`-Member wurden geändert, um, soweit möglich, Listenknoten wiederzuverwenden, anstatt hierfür die Zuordnung aufzuheben und diese dann erneut durchzuführen. Bei einem `list<int>`-Element, das bereits über die Größe 3 verfügt, werden beim Aufrufen von `assign(4, 1729)` jetzt die „ints“ auf den ersten drei Listenknoten überschrieben. Außerdem wird ein neuer Listenknoten mit dem Wert 1729 zugeordnet, anstatt die Zuordnung für alle drei Listenknoten aufzuheben und dann vier neue Listenknoten mit dem Wert 1729 zuzuordnen.

- Alle `erase(begin(), end())`-Aufrufe der Standardbibliothek wurden in `clear()` geändert.

- Mit `std::vector` werden Elemente in bestimmten Fällen jetzt effizienter initialisiert und gelöscht.

- `std::variant` wurde verbessert und kann daher leichter optimiert werden. Dies führt zu besserem generierten Code. Codeinlining mit `std::visit` ist nun deutlich effizienter.

## <a name="c-ide"></a>C++-IDE

### <a name="live-share-c-support"></a>C++-Unterstützung für Live Share

[Live Share](/visualstudio/liveshare/) unterstützt nun C++ und ermöglicht es Entwicklern, die Visual Studio oder Visual Studio Code verwenden, in Echtzeit zusammenzuarbeiten. Weitere Informationen finden Sie unter [Announcing Live Share for C++: Real-Time Sharing and Collaboration (Ankündigung: Live Share für C++ ermöglicht Austausch von Codeinformationen und Zusammenarbeit)](https://devblogs.microsoft.com/cppblog/cppliveshare/).

### <a name="intellicode-for-c"></a>IntelliCode für C++

IntelliCode ist eine optionale Erweiterung (als Workloadkomponente in 16.1 hinzugefügt), die durch umfassendes eigenständiges Training und mithilfe Ihres Codekontexts Codeelemente, die Sie vermutlich häufig verwenden, am Anfang der Vervollständigungsliste anzeigt. Dadurch müssen Sie oft nicht in der Liste nach unten scrollen. IntelliCode eignet sich für C++ insbesondere dann, wenn häufig eingesetzte Bibliotheken wie die Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [AI-Assisted Code Completion Suggestions Come to C++ via IntelliCode (IntelliCode stellt für C++ KI-gestützte Codevervollständigungsvorschläge bereit)](https://devblogs.microsoft.com/cppblog/cppintellicode/).

### <a name="template-intellisense"></a>IntelliSense für Vorlagen

Für die **Vorlagenleiste** wird nun die **Vorschaufenster**-Benutzeroberfläche anstelle eines modalen Fensters verwendet. Außerdem unterstützt die Vorlagenleiste verschachtelte Vorlagen und füllt alle Standardargumente im **Vorschaufenster** vorab aus. Weitere Informationen finden Sie unter [Template IntelliSense Improvements for Visual Studio 2019 Preview 2 (IntelliSense-Verbesserungen für Vorlagen in Vorschauversion 2 von Visual Studio 2019)](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/). Mit der Dropdownliste **Zuletzt verwendet** in der **Vorlagenleiste** können Sie schnell zwischen vorherigen Beispielargumenten wechseln.

### <a name="new-start-window-experience"></a>Neues Startfenster

Wenn Sie die IDE starten, wird ein neues Startfenster angezeigt. Dieses enthält Optionen, mit denen Sie die zuletzt geöffneten Projekte öffnen oder Code aus der Quellcodeverwaltung klonen können. Außerdem haben Sie die Möglichkeit, lokalen Code als Projektmappe oder Ordner zu öffnen oder ein neues Projekt zu erstellen. Auch das Dialogfeld „Neues Projekt“ wurde angepasst. In diesem können Sie nun Suchvorgänge ausführen und Ergebnisse filtern.

### <a name="new-names-for-some-project-templates"></a>Umbenennung mehrerer Projektvorlagen

Mehrere Projektvorlagennamen und -beschreibungen wurden so geändert, dass sie zum aktualisierten Dialogfeld „Neues Projekt“ passen.

### <a name="various-productivity-improvements"></a>Features zur Produktivitätssteigerung

Die folgenden Features in Visual Studio 2019 unterstützen Sie dabei, leichter und intuitiver zu programmieren:

- Schnellkorrekturen für folgende Aufgaben:
  - Hinzufügen fehlender #include-Anweisungen
  - Umwandeln von NULL in nullptr
  - Add missing semicolon
  - Auflösen fehlender Namespaces oder Bereiche
  - Ersetzen ungültiger Dereferenzierungsoperanden (\* in & und & in \*)
- Anzeigen einer QuickInfo für einen Block, sobald mit dem Mauszeiger auf eine schließende geschweifte Klammer gezeigt wird
- Anzeigen der Vorschau für eine Header-/Codedatei
- Öffnen einer Datei durch Verwenden von „Zur Definition wechseln“ für #include-Anweisungen

Weitere Informationen finden Sie unter [C++ Productivity Improvements in Visual Studio 2019 Preview 2 (C++-Produktivitätsfeatures in Vorschauversion 2 von Visual Studio 2019)](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/).

**Visual Studio 2019-Version 16.1**

### <a name="quickinfo-improvements"></a>QuickInfo-Verbesserungen

Für die QuickInfo wird jetzt die semantische Farbgebung Ihres Editors berücksichtigt. Außerdem verfügt sie über den neuen Link **Online suchen**, mit dem nach Onlinedokumenten gesucht wird, um mehr Informationen zum jeweiligen Codekonstrukt zu erhalten. Für rot unterschlängelten Code sucht der Link in der QuickInfo online nach dem Fehler. Auf diese Weise müssen Sie die Nachricht nicht erneut in Ihren Browser eingeben. Weitere Informationen finden Sie unter [Quick Info Improvements in Visual Studio 2019: Colorization and Search Online](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/) (QuickInfo-Verbesserungen in Visual Studio 2019: Farbgebung und Onlinesuche).

### <a name="intellicode-available-in-c-workload"></a>In C++-Workload verfügbarer IntelliCode

IntelliCode ist jetzt als optionale Komponente in der Workload **Desktopentwicklung mit C++** enthalten. Weitere Informationen finden Sie unter [Improved C++ IntelliCode now Ships with Visual Studio 2019](https://devblogs.microsoft.com/cppblog/) (Verbesserter C++ IntelliCode ist jetzt in Visual Studio 2019 enthalten).

## <a name="cmake-support"></a>CMake-Unterstützung

- Unterstützung für CMake 3.14

- Visual Studio kann nun vorhandene CMake-Caches öffnen, die von externen Tools wie CMakeGUI, benutzerdefinierten Metabuildsystemen oder Buildskripts generiert werden, die „cmake.exe“ selbst aufrufen.

- Verbesserte IntelliSense-Leistung.

- Der neue Editor für Einstellungen stellt eine Alternative zum manuellen Bearbeiten der Datei „CMakeSettings.json“ dar. Die Funktionen ähneln denen von CMakeGUI.

- Visual Studio unterstützt Sie bei den ersten Entwicklungsschritten mit C++ und CMake unter Linux, indem ermittelt wird, ob Sie über eine kompatible Version von CMake auf Ihrem Linux-Computer verfügen. Falls keine vorhanden ist, kann sie nach Rückfrage automatisch installiert werden.

- Inkompatible Einstellungen in CMakeSettings, etwa nicht passende Architekturen oder inkompatible CMake-Generatoreinstellungen, bewirken, dass Wellenlinien im JSON-Editor und Fehler in der Fehlerliste angezeigt werden.

- Die vcpkg-Toolkette wird für CMake-Projekte, die in der IDE geöffnet werden, sobald `vcpkg integrate install` ausgeführt wurde, automatisch erkannt und aktiviert. Dieses Verhalten kann deaktiviert werden, indem eine leere Toolkettendatei in CMakeSettings angegeben wird.

- Für CMake-Projekte wird „Nur eigenen Code“-Debuggen jetzt standardmäßig aktiviert.

- Warnungen bei statischer Analyse können nun im Hintergrund verarbeitet und im Editor für CMake-Projekte angezeigt werden.

- Es wurden eindeutigere build- und konfigurationsbezogene „begin“- und „end“-Nachrichten für CMake-Projekte hinzugefügt. Außerdem wird die Buildstatusanzeige von Visual Studio nun unterstützt. Zusätzlich gibt es nun unter **Extras > Optionen** eine CMake-Ausführlichkeitseinstellung, um den Detaillierungsgrad der CMake-Build- und -Konfigurationsmeldungen für das Ausgabefenster anzupassen.

- Die Einstellung `cmakeToolchain` wird jetzt in der Datei „CMakeSettings.json“ unterstützt, damit Sie Toolketten angeben können, ohne die CMake-Befehlszeile manuell zu ändern.

- Mit **STRG+UMSCHALTTASTE+B** ist nun eine neue Menüverknüpfung für **Alle erstellen** verfügbar.

**Visual Studio 2019-Version 16.1**

- Integrierte Unterstützung für die Bearbeitung, die Erstellung und das Debugging von CMake-Projekten mit Clang/LLVM. Weitere Informationen finden Sie unter [Clang/LLVM Support in Visual Studio](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/) (Clang/LLVM-Unterstützung in Visual Studio).

## <a name="linux-and-wsl"></a>Linux und WSL

**Visual Studio 2019-Version 16.1**

- Unterstützung für [AddressSanitizer (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) in plattformübergreifenden Linux- und CMake-Projekten. Weitere Informationen finden Sie unter [AddressSanitizer (ASan) for the Linux Workload in Visual Studio 2019](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/) (AddressSanitizer (ASan) für die Linux-Workload in Visual Studio 2019).

- Integrierte Visual Studio-Unterstützung für die Verwendung von C++ mit dem Windows-Subsystem für Linux (WSL). Weitere Informationen finden Sie unter [C++ with Visual Studio 2019 and Windows Subsystem for Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/) (C++ mit Visual Studio 2019 und Windows-Subsystem für Linux (WSL)).

## <a name="incredibuild-integration"></a>IncrediBuild-Integration

IncrediBuild ist jetzt als optionale Komponente in der Workload **Desktopentwicklung mit C++** enthalten. Der IncrediBuild Build Monitor ist vollständig in die Visual Studio-IDE integriert. Weitere Informationen finden Sie unter [Visualize your build with IncrediBuild’s Build Monitor and Visual Studio 2019](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/) (Visualisieren Ihres Builds per IncrediBuild Build Monitor und Visual Studio 2019).
 
## <a name="debugging"></a>Debuggen

- Für C++-Anwendungen unter Windows werden PDB-Dateien jetzt in einem separaten 64-Bit-Prozess geladen. Diese Änderung behebt eine Reihe von Abstürzen, die dadurch verursacht wurden, dass dem Debugger beim Debuggen von Anwendungen, die eine große Anzahl von Modulen und PDB-Dateien enthielten, nicht mehr genügend Arbeitsspeicher zur Verfügung stand.

- Die Suche wird in den Fenstern **Überwachen**, **Auto** und **Lokal** aktiviert.

## <a name="windows-desktop-development-with-c"></a>Windows Desktop-Entwicklung mit C++

- Die folgenden C++-ATL/MFC-Assistenten sind nicht mehr verfügbar:

  - ATL COM+ 1.0 Komponenten-Assistent
  - ATL-Assistent für Active Server Pages-Komponenten
  - ATL-OLE DB-Anbieter-Assistent
  - ATL-Eigenschaftenseiten-Assistent
  - ATL-OLE DB-Consumer-Assistent
  - MFC-ODBC-Consumer
  - MFC-Klasse aus ActiveX-Steuerelement
  - MFC-Klasse aus Typbibliothek

  Beispielcode für diese Technologien ist in der Microsoft-Dokumentation und im VCSamples-GitHub-Repository archiviert.

- Das Windows 8.1 SDK ist nicht mehr im Visual Studio-Installer verfügbar. Empfohlen wird ein Upgrade von C++-Projekten auf das neueste Windows 10 SDK. Wenn eine erforderliche Abhängigkeit zu 8.1 besteht, können Sie das SDK aus dem Windows SDK-Archiv herunterladen.

- Windows XP als Ziel ist für den neuesten C++-Toolset nicht mehr verfügbar. XP wird als Ziel mit MSVC-Compiler und -Bibliotheken in der Version für Visual Studio 2017 weiterhin unterstützt und kann über „Einzelne Komponenten“ installiert werden.

- In der Dokumentation wird aktiv von einer Verwendung von Mergemodulen für die Bereitstellung von Visual C++ Runtime abgeraten. In diesem Release werden zusätzlich MSM-Dateien als veraltet gekennzeichnet. Sie sollten erwägen, Ihre zentrale VCRuntime-Bereitstellung von MSMs zum Redistributable Package zu migrieren.

## <a name="mobile-development-with-c-android-and-ios"></a>Mobile Entwicklung mit C++ (Android und iOS)

Die C++-Android-Erfahrung verwendet jetzt standardmäßig das Android SDK 25 und Android NDK 16b.

## <a name="clangc2-platform-toolset"></a>Clang/C2-Plattformtoolset

Die experimentelle Komponente „Clang/C2“ wurde entfernt. Verwenden Sie das MSVC-Toolset für vollständige Konformität mit den C++-Standards, und nutzen Sie dabei `/permissive-` und `/std:c++17` oder die Clang/LLVM-Toolkette für Windows.

## <a name="code-analysis"></a>Codeanalyse

- Die Codeanalyse wird jetzt automatisch im Hintergrund ausgeführt. Warnungen werden während der Eingabe als grüne Wellenlinien im Editor angezeigt. Weitere Informationen finden Sie unter [In-editor code analysis in Visual Studio 2019 Preview 2 (Codeanalyse im Editor in Vorschauversion 2 von Visual Studio 2019)](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/).

- Neue, experimentelle ConcurrencyCheck-Regeln für bekannte Standardbibliothekstypen des \<mutex>-Headers sind nun verfügbar. Weitere Informationen finden Sie unter [Concurrency Code Analysis in Visual Studio 2019 (Codeanalyse für parallele Programmierung in Visual Studio 2019)](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/).

- Eine aktualisierte Teilimplementierung der [Lebensdauerprofil-Prüfung](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/) ist nun verfügbar, um verbleibende Zeiger und Referenzen zu erkennen. Weitere Informationen finden Sie unter [Lifetime Profile Update in Visual Studio 2019 Preview 2 (Lebensdauerprofil-Aktualisierung in Vorschauversion 2 von Visual Studio 2019)](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/).

- Weitere Überprüfungen für Coroutinen wie C26138, C26810, C26811 und die experimentelle Regel C26800 sind nun verfügbar. Weitere Informationen finden Sie unter [New Code Analysis Checks in Visual Studio 2019: use-after-move and coroutine (Neue Codeanalysen in Visual Studio 2019: Überprüfungen für Coroutinen und für die Verwendung von Objekten nach Nutzung der Move-Semantik)](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/).

**Visual Studio 2019-Version 16.1**

Neue Schnellkorrekturen für nicht initialisierte Variablenüberprüfungen. Weitere Informationen finden Sie unter [New code analysis quick fixes for uninitialized memory (C6001) and use before init (C26494) warnings](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/) (Neue Codeanalyse-Schnellkorrekturen für nicht initialisierten Speicher (C6001) und Verwendung vor der Initialisierung (C26494) von Warnungen).

## <a name="unit-testing"></a>Komponententest

Die Vorlage für verwaltete C++-Testprojekte (Managed C++ Test Project) ist nicht mehr verfügbar. Sie können aber weiterhin das Framework für verwaltete C++-Tests für Ihre vorhandenen Projekte einsetzen. Für neue Komponententests sollten Sie eines der nativen Testframeworks (MSTest, Google Test) verwenden, für das Visual Studio Vorlagen bereitstellt. Alternativ können Sie auch die Vorlage für verwaltete C#-Testprojekte nutzen.
