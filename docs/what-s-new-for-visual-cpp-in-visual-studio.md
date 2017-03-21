---
title: Neuerungen bei Visual C++ in Visual Studio&2015; | Microsoft-Dokumentation
ms.custom: 
ms.date: 3/7/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: d3ac5f5e54334e42ad48304d26a4f32b1b598459
ms.openlocfilehash: dbed9eaf443d7392373d1eeba81bc0095c5bd1b4
ms.lasthandoff: 03/07/2017

---

# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Neuerungen bei Visual C++ in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] bietet für die Visual C++-Umgebung zahlreiche Updates und Korrekturen. Wir haben mehr als 250 Fehler und gemeldete Probleme mit dem Compiler und den Tools behoben, von denen viele durch Kunden über [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect") übermittelt wurden. Vielen Dank für das Melden von Fehlern!  Weitere Informationen zu Neuerungen im gesamten Visual Studio finden Sie unter [Neuerungen bei [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]] (https://go.microsoft.com/fwlink/?linkid=834481).

<!--The compiler and tools version number in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] is 14.10.24629. -->


## <a name="c-compiler"></a>C++ Compiler

### <a name="c-conformance-improvements"></a>Verbesserungen an C++ bei der Übereinstimmung mit Standards
In dieser Version haben wir den C++-Compiler und die Standardbibliothek mit erweiterter Unterstützung für C++11- und C++14-Features aktualisiert und bieten vorläufige Unterstützung für bestimmte Features, die im C++17-Standard erwartet werden. Ausführliche Informationen finden Sie unter [Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual C++ 2017](cpp-conformance-improvements-2017.md).

### <a name="new-compiler-switches"></a>Neue Compilerschalter  

 -**/std:c++14** und **/std:c++latest**: Diese Compilerschalter ermöglichen Ihnen das Verwenden bestimmter Versionen der Programmiersprache ISO C++ in einem Projekt. Weitere Informationen finden Sie im Blogbeitrag [Standards version switches in the compiler](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/standards-version-switches-in-the-compiler). Die meisten Standardfeatures des neuen Entwurfs werden vom Schalter /std:c++latest geschützt. 

-[/permissive-](build/reference/permissive-standards-conformance.md): Aktiviert alle strengen Compileroptionen für die Übereinstimmung mit Standards und deaktiviert die meisten Microsoft-spezifischen Compilererweiterungen [aber z.B. nicht __declspec(dllimport)]. (Standardmäßig deaktiviert, wird aber zu einem bestimmten Zeitpunkt in der Zukunft aktiviert.)

-[/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): Aktiviert die Anzeige der Zeilennummer, der Zeilennummer und Spalte oder der Zeilennummer, Spalte und eines Caretzeichens unter der Codezeile, in der der Diagnosefehler oder die Warnung gefunden wurde.

-[/debug:fastlink](build/reference/debug-generate-debug-info.md):  
Ermöglicht um bis zu 30 % schnellere inkrementelle Verknüpfungszeiten (im Vergleich mit Visual Studio 2015), indem nicht alle Debuginformationen in die PDB-Datei kopiert werden. Die PDB-Datei zeigt stattdessen auf die Debuginformationen für das Objekt und die Bibliotheksdateien, die zum Erstellen der ausführbaren Datei verwendet wurden. Siehe die Blogbeiträge [Faster C++ build cycle in VS “15” with /Debug:fastlink](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) und [Recommendations to speed C++ builds in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] ermöglicht das Verwenden von /sdl mit /await. Die /RTC-Einschränkung mit Coroutinen wurde beseitigt. 

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, Sicherheit, Diagnose und Versionsverwaltung
Diese Version bietet mehrere Verbesserungen hinsichtlich Optimierung, Codegenerierung, Versionsverwaltung für das Toolset und Diagnose. Zu diesen Verbesserungen gehören folgende:  

- Verbesserte Codegenerierung von Schleifen: Unterstützung der automatischen Vektorisierung der Division von konstanten ganzen Zahlen, bessere Identifizierung von memset-Mustern.
- Verbesserte Codesicherheit: verbesserte Ausgabe der Compilerdiagnose eines Pufferüberlaufs, und /guard:cf schützt jetzt switch-Anweisungen, die Sprungtabellen generieren.
- Versionsverwaltung: Der Wert des integrierten Präprozessormakros _MSC_VER wird nun bei jedem Update des Visual C++-Toolsets monoton aktualisiert. Weitere Informationen finden Sie unter [Visual C++-Compilerversion](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Neues Layout des Toolsets: Der Compiler und verwandte Buildtools haben auf dem Entwicklungscomputer einen neuen Speicherort und eine neue Verzeichnisstruktur. Das neue Layout ermöglicht die parallele Installation mehrerer Versionen des Compilers. Weitere Informationen finden Sie unter [Layout der Compilertools in Visual Studio „15“](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Verbesserte Diagnose: Das Ausgabefenster zeigt jetzt die Spalte, in der ein Fehler auftritt. Weitere Informationen finden Sie im Blogbeitrag [C++ compiler diagnostics improvements in VS „15“ Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Bei Verwendung von Co-Routinen wurde das experimentelle Schlüsselwort "yield" (verfügbar unter dem Schalter „/await“) entfernt. Der Code sollte so aktualisiert werden, dass stattdessen „co_yield“ verwendet wird. Weitere Informationen finden Sie im Visual C++-Teamblog. 

## <a name="c-libraries"></a>C++-Bibliotheken

### <a name="standard-library-improvements"></a>Verbesserungen der Standardbibliothek:

* Kleinere Verbesserungen bei der Diagnose „basic_string _ITERATOR_DEBUG_LEVEL != 0“. Das Auslösen einer IDL-Überprüfung in einer Zeichenfolgenmaschine meldet nun das bestimmte Verhalten, das die Überprüfung ausgelöst hat. Anstelle von „string iterator not dereferencable“ (Zeichenfolgeniterator nicht dereferenzierbar), erhalten Sie „cannot dereference string iterator because it is out of range (e.g. an end iterator)“ (Zeichenfolgeniterator ist nicht dereferenzierbar, da er sich außerhalb des Bereichs befindet (z.B. ein End-Iterator)).
* Leistungsverbesserung: dadurch überlädt „basic_string::find(char)“ nur „call traits::find once“. Dies wurde zuvor als eine allgemeine Zeichenfolgensuche nach einer Zeichenfolge der Länge 1 implementiert.
* Leistungsverbesserung: „basic_string::operator==“ überprüft nun die Größe der Zeichenfolge, bevor der Inhalt der Zeichenfolge verglichen wird.
* Leistungsverbesserung: die Kontrollkopplung in basic_string, die für den Compileroptimierer schwer zu analysieren war, wurde entfernt. Löst VSO# 262848 auf: „<string>: reserve() does too much work“ (reserve() arbeitet zu viel). Beachten Sie, dass bei kurzen Zeichenfolgen der Aufruf von „reserve“ auch dann Kosten verursacht, wenn keine Arbeit erledigt wird.
* Wir haben \<any\>, \<string_view\>, apply(), make_from_tuple() hinzugefügt.
* std::vector wurde aufgrund der Korrektheit und Leistung überholt: Das Aliasing während der Einfügung / des Einbaus wird nun korrekt gehandhabt, so wie dies von Standard vorgesehen ist. Die starke Ausnahmegarantie wird nun bereitgestellt, wenn Standard dies durch move_if_noexcept() oder eine andere Logik erfordert. Die Einfügung / der Einbau führen weniger Elementvorgänge durch.
* Die C++-Standardbibliothek vermeidet nun die Dereferenzierung von Fancy Pointern des Typs NULL.
* \<optional\>, \<variant\>, „shared_ptr::weak_type“ und \<cstdalign\> wurden hinzugefügt.
* C++14 constexpr in „min/max/minmax(initializer_list)“ und „min_element/max_element/minmax_element()“ wurden aktiviert.
* Die Leistung von „weak_ptr::lock()“ wurde verbessert.
* Der Bewegungszuweisungsoperator „std::promise“, der zuvor zum dauerhaften Blockieren von Code führen konnte, wurde korrigiert.
* Compilerfehler mit der impliziten Konvertierung von atomic\<T \*\> in T\* wurden behoben.
* „pointer_traits\<Ptr\>“ erkennt „Ptr::rebind\<U\>“ nun korrekt.
* Ein fehlender Konstantenqualifizierer im Subtraktionsoperator von „move_iterator“ wurde behoben.
* Die lautlose Generierung von ungültigem Code für zustandsbehaftete benutzerdefinierte Allokatoren, die „propagate_on_container_copy_assignment“ und „propagate_on_container_move_assignment“ anfordern, wurde behoben.
* „atomic\<T\>“ toleriert nun überladene „operator&()“.
* Header der C++-Standardbibliothek vermeiden nun das Einschließen von Deklarationen für unnötige intrinsische Compilerfunktionen, um den Compilerdurchsatz zu erhöhen.
* Compilerdiagnosen für falsche „bind()“-Aufrufe wurden leicht verbessert.
* Die Leistung des Bewegungskonstruktors von std::string/std::wstring wurde um mehr als das Dreifache verbessert.
* Eine vollständige Liste der STL-Optimierungen finden Sie im Blog unter [STL Fixes In VS 2017 RTM](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/).

### <a name="open-source-library-support"></a>Unterstützung für Open-Source-Bibliotheken  
Vcpkg ist ein Open-Source-Befehlszeilentool, das den Prozess des Beziehens und Erstellens von statischen C++-Open-Source Bibliotheken und DLLs in Visual Studio sehr stark vereinfacht. Weitere Informationen finden Sie im Blogbeitrag [Vcpkg updates: Static linking is now available](https://blogs.msdn.microsoft.com/vcblog/2016/11/01/vcpkg-updates-static-linking-is-now-available/).

### <a name="cpprest-sdk-290"></a>C++ REST SDK 2.9.0  
Das C++ REST SDK, eine plattformübergreifende Web-API für C++, wurde auf Version 2.9.0 aktualisiert. Weitere Informationen finden Sie im Blogbeitrag [CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL
* Weitere Korrekturen an der Übereinstimmung bei der Suche nach Namen
* Vorhandene Bewegungskonstruktoren und Bewegungszuweisungsoperatoren werden jetzt ordnungsgemäß als nicht auslösend markiert.
* Die gültige Warnung C4640 zur threadsicheren Initialisierung von lokalen statischen Variablen in „atlstr.h“ wird nicht mehr unterdrückt.
* Die threadsichere Initialisierung lokaler statischer Variablen wurde bei [Verwendung von ATL UND Erstellen einer DLL] im XP-Toolset automatisch deaktiviert. Dies ist nun nicht mehr der Fall. Wenn Sie die threadsichere Initialisierung ausschalten möchten, können Sie „/Zc:threadSafeInit-“ in Ihren Projekteinstellungen hinzufügen. 

### <a name="visual-c-runtime"></a>Visual C++-Runtime
* Neuer Header „cfguard.h“ für Ablaufsteuerungsschutz-Symbole. 

## <a name="c-ide"></a>C++-IDE

* Die Leistung bei Konfigurationsänderungen ist jetzt für native C++-Projekte besser und für C++-/CLI-Projekte viel besser. Wenn eine Projektmappenkonfiguration zum ersten Mal aktiviert wird, ist sie jetzt schneller, und alle nachfolgenden Aktivierungen dieser Projektmappenkonfiguration erfolgen fast unmittelbar.

### <a name="intellisense"></a>Intellisense  
* Das neue, auf SQLite basierende Datenbankmodul wird jetzt standardmäßig verwendet. Dadurch werden Datenbankoperationen wie „Gehe zu Definition“ und „Alle Verweise suchen“ beschleunigt, und die Zeit für die erstmalige Analyse einer Projektmappe verkürzt sich erheblich. Die Einstellung wurde nach „Extras“ > „Optionen“ > „Texteditor“ > „C/C++“ > „Erweitert“ verschoben (sie befand sich bisher unter ...„C/C++“ > „Experimentell“).

* Wir haben die IntelliSense-Leistung für Projekte und Dateien verbessert, die keine vorkompilierten Header verwenden. Ein automatisch vorkompilierter Header wird für Header in der aktuellen Datei erstellt.

* Wir haben die Fehlerfilterung und Hilfe für IntelliSense-Fehler in der Fehlerliste hinzugefügt. Das Klicken auf die Fehlerspalte ermöglicht jetzt die Filterung. Durch Klicken auf die einzelnen Fehler oder durch Drücken von F1 wird eine Onlinesuche nach der Fehlermeldung gestartet.

  ![Fehlerliste](media/ErrorList1.png "Fehlerliste")

  ![Fehlerliste gefiltert](media/ErrorList2.png "Fehlerliste gefiltert")

* Die Möglichkeit zum Filtern von Elementen der Memberliste nach Typ wurde hinzugefügt.

  ![Filterung der Memberliste](media/mlfiltering.png "Filterung der Memberliste")

* Eine neue experimentelle, vorhersehbare IntelliSense-Funktion, die das kontextbewusste Filtern in der Memberliste bereitstellt, wurde hinzugefügt. Siehe den Blogbeitrag [C++ IntelliSense Improvements – Predictive IntelliSense & Filtering](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/).

* „Alle Verweise suchen (UMSCHALT+F12)“ ermöglicht nun eine einfachere Navigation, auch in komplexen Codebasen. Das Feature bietet eine erweiterte Gruppierung, Filterung, Sortierung, Suche in Ergebnissen und (für einige Sprachen) eine Einfärbung, damit Sie Ihre Verweise umfassend verstehen können. Für C++ enthält die neue Benutzeroberfläche Informationen dazu, ob Informationen aus einer Variablen gelesen oder in eine Variable geschrieben werden.

* Die Punkt-zu-Pfeil-Funktion von IntelliSense wurde aus „experimentell“ in „erweitert“ verschoben und ist nun standardmäßig aktiviert. Die Editor-Funktionen „Erweiterungsbereiche“ und „Erweiterungsrangfolge“ wurden auch von „experimentell“ zu „erweitert“ verschoben.

* Die experimentellen Refactoringfeatures „Signatur ändern“ und „Funktion extrahieren“ sind nun standardmäßig verfügbar.

* Wir haben das neue experimentelle Feature „Schnelleres Laden von Projekten“ für C++-Projekte aktiviert. Wenn Sie das nächste Mal ein C++-Projekt öffnen, wird es schneller geladen und das darauffolgende Mal wird es richtig schnell geladen!

Einige dieser Features sind auch in anderen Sprachen gängig, während einige C++-spezifisch sind. Weitere Informationen zu diesen neuen Features finden Sie im Blogbeitrag [Announcing Visual Studio “15”](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/). 

### <a name="support-for-non-msbuild-projects-with-open-folder"></a>Unterstützung für Nicht-MSBuild-Projekte mit „Ordner öffnen“
In Visual Studio 2017 wurde das Feature „Ordner öffnen“ eingeführt, das Ihnen das Programmieren, Erstellen von Builds und Debuggen in einem Ordner mit Quellcode ermöglicht, ohne dass Projektmappen oder Projekte erstellt werden müssen. Dadurch wird der Einstieg in Visual Studio wesentlich einfacher, selbst wenn Ihr Projekt kein auf MSBuild basierendes Projekt ist. Mit „Ordner öffnen“ erhalten Sie Zugang zu den Funktionen zum Verstehen, Bearbeiten, Erstellen und Debuggen von Code, die Visual Studio bereits für MSBuild-Projekte bietet. Weitere Informationen finden Sie im Blogbeitrag [Bring your C++ codebase to Visual Studio with “Open Folder”](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/bring-your-c-codebase-to-visual-studio-with-open-folder/).

* Verbesserungen in der Benutzeroberfläche „Ordner öffnen“. Sie können die Oberfläche über diese JSON-Dateien anpassen:
  -    CppProperties.json zum Anpassen des IntelliSense- und Browsererlebnisses.
  -    Tasks.json zum Anpassen der Buildschritte. 
  -    Launch.json zum Anpassen des Debugvorgangs.

### <a name="cmake-support-via-open-folder"></a>Unterstützung von CMake über „Ordner öffnen“
Visual Studio 2017 führt die Unterstützung für die Verwendung von CMake-Projekten ohne Konvertierung in MSBuild-Projektdateien (.vcxproj) ein. Weitere Informationen finden Sie unter [CMake-Unterstützung in Visual Studio 2017](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/cmake-support-in-visual-studio/) und [CMake support in Visual Studio 2017 – what’s new in the RC.2 update (CMake-Support in Visual Studio 2017 – Neues im RC.2-Update)](https://blogs.msdn.microsoft.com/vcblog/2016/12/20/cmake-support-in-visual-studio-2017-whats-new-in-the-rc-update/). Durch Öffnen von CMake-Projekten mit „Ordner öffnen“ wird die Umgebung für die Bearbeitung, Erstellung und das Debuggen von C++ automatisch konfiguriert.

* C++ IntelliSense funktioniert, ohne dass Sie eine Datei „CppProperties.json“ im Stammordner erstellen müssen. Darüber hinaus haben wir ein neues Dropdownmenü hinzugefügt, sodass Benutzer einfach zwischen von CMake - und CppProperties.json-Dateien bereitgestellten Konfigurationen wechseln können.

* Weitere Konfigurationen werden über eine Datei „CMakeSettings.json“ unterstützt, die sich im gleichen Ordner wie die Datei „CMakeLists.txt“ befindet.

  ![„Ordner öffnen“ von Cmake](media/cmake_cpp.png "„Ordner öffnen“ von Cmake")


## <a name="c-installation-workloads"></a>Arbeitsauslastungen der C++-Installation 

### <a name="windows-desktop-development-with-c"></a>Windows-Desktopentwicklung mit C++:  
Die Installationsoberfläche ermöglicht bei der Installation der ursprünglichen C++-Arbeitsauslastung jetzt eine feinere Abstimmung. Wir haben auswählbare Komponenten hinzugefügt, sodass Sie nur die Tools installieren können, die Sie benötigen.  Beachten Sie, dass die angegebenen Installationsgrößen für die im Installationsprogramm aufgeführten Komponenten nicht genau sind und die Gesamtgröße unterschätzen.

Wenn Sie Win32-Projekte erfolgreich in der C++-Desktoparbeitsauslastung erstellen möchten, müssen Sie ein Toolset und ein Windows SDK installieren. Zum Installieren der empfohlenen (ausgewählten) Komponenten benötigen Sie „VC++ 2017 c141 Toolset (x86, x64)“ und „Windows 10 SDK (10.0.14393)“. Sollten die nötigen Tools nicht installiert sein, können Projekte nicht erfolgreich erstellt werden. Außerdem wird der Assistent nicht mehr reagieren.

### <a name="linux-development-with-c"></a>Linux-Entwicklung mit C++:  
Die beliebte Erweiterung [Visual C++ für Linux-Entwicklung](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) ist nun Bestandteil von Visual Studio. Diese Installation bietet alles, was Sie zum Entwickeln und Debuggen von C++-Anwendungen in einer Linux-Umgebung benötigen.  

### <a name="game-development-with-c"></a>Spieleentwicklung mit C++:  
Verwenden Sie die volle Leistung von C++, um professionelle Spiele zu erstellen, die von DirectX oder Cocos2d unterstützt werden.  

### <a name="mobile-development-with-c-android-and-ios"></a>Mobile Entwicklung mit C++ (Android und iOS):  
Sie können nun mithilfe von Visual Studio mobile Apps erstellen und debuggen, die auf Android und iOS ausgerichtet sind.  

### <a name="universal-windows-apps"></a>Universelle Windows-Apps:  
C++ wird als optionale Komponente für die Arbeitsauslastung der Universellen Windows-App bereitgestellt.  Upgrades von C++-Projekten müssen zurzeit manuell ausgeführt werden. Wenn Sie ein auf UWP-Projekt mit dem Ziel v140 in Visual Studio 2017 öffnen, müssen Sie das v141-Plattformtoolset auf den Projekteigenschaftenseiten auswählen, wenn Visual Studio 2015 nicht installiert ist.

## <a name="new-options-for-c-on-universal-windows-platform"></a>Neue Optionen für C++ auf der universellen Windows-Plattform
Sie haben jetzt neue Optionen für das Schreiben und Packen von C++-Anwendungen für die universelle Windows-Plattform und den Windows Store. Sie können den Desktop App Converter zum Packen Ihrer vorhandenen Desktopanwendung für die Bereitstellung über den Windows Store nutzen. Weitere Informationen finden Sie im Blogbeitrag [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/) und unter [Überführen Ihrer Desktop-App auf die universelle Windows-Plattform (UWP) mit Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Beim Schreiben von neuem Code können Sie nun C++/WinRT verwenden. Dies ist eine C++-Standardsprachprojektion für Windows-Runtime (WinRT), die nur in Headerdateien implementiert wird. Mit ihr können Sie Windows-Runtime-APIs mit jedem C+-Compiler erstellen und nutzen, der mit Standards kompatibel ist. C++/WinRT wurde dafür konzipiert, C++-Entwicklern erstklassigen Zugriff auf die moderne Windows-API zur Verfügung zu stellen. Weitere Informationen finden Sie im Blogbeitrag [C++/WinRT Available on GitHub](https://moderncpp.com/).


## <a name="clangc2-platform-toolset"></a>Clang/C2-Plattformtoolset
Das Clang/C2-Toolset im Funktionsumfang von [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] unterstützt jetzt den Schalter „/bigobj“, der für das Erstellen großer Projekte entscheidend ist. Es umfasst außerdem eine Reihe wichtiger Programmfehlerbehebungen, sowohl im Front-End als auch im Back-End des Compilers.

## <a name="c-code-analysis"></a>C++-Codeanalyse

Visual Studio liefert nun die C++-Kernprüfungen zum Erzwingen der [C++-Kernrichtlinien](https://github.com/isocpp/CppCoreGuidelines). Aktivieren Sie die Prüfungen einfach im Dialogfeld „Code Analysis Extensions“ (Codeanalyseerweiterungen) auf den Eigenschaftenseiten des Projekts, und die Erweiterungen werden enthalten sein, wenn Sie die Codeanalyse ausführen. 

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck-Eigenschaftenseite") 

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio-Grafikdiagnose

Die Grafikdiagnose von Visual Studio umfasst eine Reihe von Tools zum Aufzeichnen und Analysieren von Rendering- und Leistungsproblemen in Direct3D-Apps. Die Features der Grafikdiagnose können für Apps verwendet werden, die lokal auf Ihrem Windows-PC, in einem Windows-Geräteemulator oder auf einem Remotecomputer oder-gerät ausgeführt werden.

* **Ein- und Ausgabe von Vertex- und Geometrieshadern:** Die Möglichkeit der Anzeige der Ein- und Ausgabe von Vertex- und Geometrieshadern war eines der am häufigsten gewünschten Features, das nun in den Tools unterstützt wird. Wählen Sie einfach die VS- oder GS-Phase in der Ansicht „Pipelinestufen“, um mit dem Untersuchen der Ein- und Ausgabe in der nachstehenden Tabelle zu beginnen.

  ![Ein-/Ausgabe für Shader](media/io-shaders.png)

* **Suchen und Filtern in der Objekttabelle:** Bietet eine schnelle und einfache Möglichkeit, die gesuchten Ressourcen zu finden.

  ![Suche](media/search.png)
   
* **Ressourcenverlauf:** Diese neue Ansicht bietet eine optimierte Möglichkeit der Ansicht des gesamten Änderungsverlaufs einer Ressource gemäß ihrer Verwendung während der Wiedergabe eines aufgezeichneten Frames. Um den Verlauf für jede Ressource aufzurufen, klicken Sie einfach auf das Uhrsymbol neben jeden Ressourcenlink.

  ![Ressourcenverlauf](media/resource-history.png)

  Hiermit wird das Toolfenster „Ressourcenverlauf“ angezeigt, in dem sich der Änderungsverlauf der Ressource befindet.

  ![Ressourcenverlaufsänderung](media/resource-history-change.png)

  Wenn Ihr Frame bei aktivierter vollständiger Aufruflistenerfassung erfasst wurde (**Visual Studio > Tools > Optionen > Grafikdiagnose**), kann der Kontext jedes einzelnen Änderungsereignisses schnell abgeleitet und innerhalb Ihres Visual Studio-Projekts überprüft werden.  

* **API-Statistiken:** Eine allgemeine Zusammenfassung der API-Verwendung in Ihrem Frame. Dies kann beim Ermitteln von Aufrufen nützlich sein, von denen Sie nicht wissen, dass sie erfolgen, oder von Aufrufen, die zu oft erfolgen. Dieses Fenster steht über **Ansicht > API Statistiken** in der Visual Studio-Grafikanalyse zur Verfügung.

  ![API-Statistiken](media/api-stats.png)

* **Speicherstatistiken:** Zeigt, wie viel Arbeitsspeicher der Treiber für die Ressourcen reserviert, die Sie im Frame erstellen. Dieses Fenster steht über „Ansicht->Speicherstatistiken“ in der Visual Studio-Grafikanalyse zur Verfügung. Daten können zum Anzeigen in einer Tabelle in eine CSV-Datei kopiert werden, indem mit der rechten Maustaste geklickt und „Alles kopieren“ ausgewählt wird.

  ![Speicherstatistiken](media/memory-stats.png)
 
* **Frame-Überprüfung:** Die neue Liste mit Fehlern und Warnungen bietet eine einfache Möglichkeit der Navigation zu Ihrer Ereignisliste basierend auf potenziellen Problemen, die auf Direct3D-Debugebene erkannt wurden. Klicken Sie zum Öffnen des Fensters in der Visual Studio-Grafikanalyse auf „Ansicht->Frame-Überprüfung“. Klicken Sie dann auf „Überprüfung ausführen“, um die Analyse zu starten. Je nach Komplexität des Frames kann dieser Vorgang mehrere Minuten dauern.

  ![Frame-Überprüfung](media/frame-validation.png)
 
* **Frame-Analyse für D3D12:** Verwenden Sie die Frame-Analyse zum Analysieren der Leistung von Zeichnen-Befehlen mit „Was-wäre-wenn“-Experimenten. Wechseln Sie zur Registerkarte „Frame-Analyse“, und führen Sie Analysen aus, um den Bericht anzuzeigen. Weitere Informationen bietet das Video [GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool).

  ![Frame-Analyse](media/frame-analysis.png)

* **Verbesserungen der GPU-Nutzung:** Öffnen Sie Ablaufverfolgungen, die über den Visual Studio-Profiler für GPU-Nutzung mit entweder dem Tool „GPU-Ansicht“ oder Windows Performance Analyzer (WPA) erstellt wurden, um eine detailliertere Analyse zu erhalten. Wenn das Windows Performance Toolkit installiert ist, sind rechts unten in der Sitzungsübersicht zwei Links vorhanden: einer für WPA und einer für die GUP-Ansicht.

  ![GPU-Nutzung](media/gpu-usage.png)
 
  Über diesen Link in der GPU-Ansicht geöffnete Ablaufverfolgungen unterstützen das synchronisierte Zoomen und Schwenken auf der Zeitachse zwischen Visual Studio und GPU-Ansicht. Ein Kontrollkästchen in Visual Studio dient zum Steuern, ob die Synchronisierung aktiviert ist oder nicht. 

  ![GPU-Ansicht](media/gpu-view.png) 


 

