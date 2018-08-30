---
title: Neuerungen bei Visual C++ in Visual Studio 2015 | Microsoft-Dokumentation
ms.date: 11/15/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d3a3ec1fec213cc6fa1bb5dc0ebfdadbe7d22b2
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131719"
---
# <a name="whats-new-for-visual-c-in-visual-studio-2017"></a>Neuerungen bei Visual C++ in Visual Studio 2017

Visual Studio 2017 RC enthält viele Updates und Problembehebungen der Visual C++-Umgebung. Es wurden mehr als 250 Probleme behoben und Probleme mit dem Compiler und Tools gemeldet. Viele Probleme wurden von Kunden über die Optionen [Problem melden](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) und [Provide a Suggestion](https://visualstudio.uservoice.com/) (Vorschlag senden) unter **Feedback senden** übermittelt. Vielen Dank für das Melden von Fehlern! Weitere Informationen zu Neuerungen in Visual Studio finden Sie unter [What's new in Visual Studio 2017 (Neuerungen in Visual Studio 2017)](https://go.microsoft.com/fwlink/p/?linkid=834481).

<!--The compiler and tools version number in Visual Studio 2017 is 14.10.24629. -->

## <a name="c-compiler"></a>C++-Compiler

### <a name="c-conformance-improvements"></a>Verbesserungen an C++ bei der Übereinstimmung mit Standards

In dieser Version haben wir den C++-Compiler und die Standardbibliothek mit erweiterter Unterstützung für C++11- und C++14-Features aktualisiert und bieten vorläufige Unterstützung für bestimmte Features, die im C++17-Standard erwartet werden. Ausführliche Informationen finden Sie unter [Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual C++ 2017](cpp-conformance-improvements-2017.md).

**Visual Studio 2017, Version 15.5:** Der Compiler unterstützt ungefähr 75 % der Features, die in C++17 neu sind (z.B. strukturierte Bindungen, `constexpr`-Lambdaausdrücke, `if constexpr`, Inlinevariablen, fold-Ausdrücke und das Hinzufügen von `noexcept` zum Typsystem). Diese Features sind unter der Option **/std:c++17** verfügbar. Weitere Informationen finden Sie unter [Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual Studio 2017](cpp-conformance-improvements-2017.md).

**Visual Studio 2017, Version 15.7:** Das MSVC-Compilertoolset in Visual Studio Version 15.7 erfüllt nun den C++-Standard. Weitere Informationen finden Sie unter [Announcing: MSVC Conforms to the C++ Standard (Ankündigung: MSVC erfüllt den C++-Standard)](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/) und [Visual C++-Sprachkonformität](visual-cpp-language-conformance.md).

### <a name="new-compiler-options"></a>Neue Compileroptionen

- [/permissive-](build/reference/permissive-standards-conformance.md): Aktiviert alle strengen Compileroptionen für die Übereinstimmung mit Standards und deaktiviert die meisten Microsoft-spezifischen Compilererweiterungen (aber z.B. nicht `__declspec(dllimport)`). Diese Option ist in Visual Studio 2017-Version 15.5 standardmäßig aktiviert.  Der Konformitätsmodus **/permissive-** schließt Unterstützung für die Zweiphasen-Namenssuche ein. Weitere Informationen finden Sie unter [Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual Studio 2017](cpp-conformance-improvements-2017.md).

- [/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): Aktiviert die Anzeige der Zeilennummer, der Zeilennummer und der Spalte oder der Zeilennummer, Spalte und eines Caretzeichens unter der Codezeile, in der der Diagnosefehler oder die Warnung gefunden wurde.

- [/debug:fastlink](build/reference/debug-generate-debug-info.md): Ermöglicht um bis zu 30 % schnellere inkrementelle Verknüpfungszeiten (im Vergleich mit Visual Studio 2015), indem nicht alle Debuginformationen in die PDB-Datei kopiert werden. Die PDB-Datei zeigt stattdessen auf die Debuginformationen für das Objekt und die Bibliotheksdateien, die zum Erstellen der ausführbaren Datei verwendet wurden. Weitere Informationen finden Sie in den Blogbeiträgen [Faster C++ build cycle in VS "15" with /Debug:fastlink (Schnellerer C++-Buildzyklus in VS „15“ mit /Debug:fastlink)](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) und [Recommendations to speed C++ builds in Visual Studio (Empfehlungen zum Beschleunigen von C++-Builds in Visual Studio)](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

- Visual Studio 2017 ermöglicht die Verwendung von [/sdl](build/reference/sdl-enable-additional-security-checks.md) mit [/await](build/reference/await-enable-coroutine-support.md). Die [/RTC](build/reference/rtc-run-time-error-checks.md)-Einschränkung mit Coroutinen wurde beseitigt.

   **Visual Studio 2017 Version 15.3**:  
- [/std:c++14 und /std:c++latest:](build/reference/std-specify-language-standard-version.md) Diese Compileroptionen ermöglichen Ihnen das Verwenden bestimmter Versionen der Programmiersprache ISO C++ in einem Projekt. Die meisten Standardfeatures des neuen Entwurfs werden von der Option **/std:c++latest** geschützt.

- [/std:c++17](build/reference/std-specify-language-standard-version.md) aktiviert die C++17-Features, die vom Compiler implementiert werden. Diese Option deaktiviert die Unterstützung von Compiler- und Standardbibliotheken für Features, die in Versionen des Arbeitsentwurfs und Fehlerbehebungsaktualisierungen des C++-Standards nach C++17 neu sind oder geändert wurden. Verwenden Sie zum Aktivieren dieser Funktionen **/std:c++latest**.


### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, Sicherheit, Diagnose und Versionsverwaltung

Dieses Release bietet mehrere Verbesserungen hinsichtlich Optimierung, Codegenerierung, Versionsverwaltung für das Toolset sowie Diagnose. Zu diesen Verbesserungen gehören folgende:

- Verbesserte Codegenerierung von Schleifen: Unterstützung der automatischen Vektorisierung der Division von konstanten ganzen Zahlen, bessere Identifizierung von memset-Mustern.
- Verbesserte Codesicherheit: Verbesserte Ausgabe der Compilerdiagnose eines Pufferüberlaufs. [/guard:cf](build/reference/guard-enable-control-flow-guard.md) schützt jetzt switch-Anweisungen, die Sprungtabellen generieren.
- Versionsverwaltung: Der Wert des integrierten Präprozessormakros **\_MSC\_VER** wird nun bei jedem Update des Visual C++-Toolsets monoton aktualisiert. Weitere Informationen finden Sie unter [Visual C++-Compilerversion](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Neues Layout des Toolsets: Der Compiler und verwandte Buildtools haben auf dem Entwicklungscomputer einen neuen Speicherort und eine neue Verzeichnisstruktur. Das neue Layout ermöglicht die parallele Installation mehrerer Versionen des Compilers. Weitere Informationen finden Sie unter [Layout der Compilertools in Visual Studio „15“](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Verbesserte Diagnose: Das Ausgabefenster zeigt jetzt die Spalte, in der ein Fehler auftritt. Weitere Informationen finden Sie im Blogbeitrag [C++ compiler diagnostics improvements in VS „15“ Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Bei Verwendung von Coroutinen wurde das experimentelle Schlüsselwort **yield** (verfügbar unter der Option **/await**) entfernt. Der Code sollte so aktualisiert werden, dass stattdessen `co_yield` verwendet wird. Weitere Informationen finden Sie im [Visual C++-Blog](https://blogs.msdn.microsoft.com/vcblog/).

**Visual Studio 2017 Version 15.3**:

Weitere Verbesserungen der Diagnose im Compiler. Weitere Informationen finden Sie unter [Diagnostic Improvements in Visual Studio 2017 15.3.0](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/) (Verbesserungen bei der Diagnose in Visual Studio 2017 15.3.0).

**Visual Studio 2017 Version 15.5**:

Die Visual C++-Laufzeitleistung wird weiterhin aufgrund besser generierter Codequalität verbessert. Das bedeutet, dass Sie Ihren Code einfach neu kompilieren können, und Ihre App wird schneller ausgeführt. Einige der Compileroptimierungen sind brandneu, z.B. die Vektorisierung von bedingten skalaren Speichern, die Kombination der Aufrufe `sin(x)` und `cos(x)` in einem neuen Aufruf `sincos(x)` und die Beseitigung von redundanten Anweisungen aus dem SSA-Optimierer. Andere Compileroptimierungen sind Verbesserungen an bestehenden Funktionen wie Vektorisierungsheuristiken für bedingte Ausdrücke, bessere Schleifenoptimierungen und float min/max-codegen. Der Linker verfügt über eine neue und schnellere **/OPT:ICF**-Implementierung, die die Linkzeit um bis zu 9 % beschleunigen kann, und es sind weitere Leistungsoptimierungen für „inkrementelles Verknüpfen“ vorhanden. Weitere Informationen finden Sie unter [/OPT (Optimierungen)](https://docs.microsoft.com/en-us/cpp/build/reference/opt-optimizations) und [/INCREMENTAL (inkrementelles Verknüpfen)](https://docs.microsoft.com/en-us/cpp/build/reference/incremental-link-incrementally).

Visual C++ unterstützt AVX-512 von Intel, einschließlich der Vector Length-Anweisungen, die neue Funktionen in AVX-512 für 128 und 256 Bit breite Register bereitstellen.

Die Option [/Zc:noexceptTypes-](build/reference/zc-noexcepttypes.md) kann verwendet werden, um zur C++14-Version von `noexcept` zurückzukehren, während der C++17-Modus im Allgemeinen verwendet wird. Dies ermöglicht es Ihnen, Ihren Quellcode zu aktualisieren, um ihn an C++17 anzupassen, ohne dass Sie Ihren gesamten `throw()`-Code zur gleichen Zeit neu schreiben müssen. Weitere Informationen dazu finden Sie unter [Entfernen der dynamischen Ausnahmespezifikation und noexcept](cpp-conformance-improvements-2017.md#noexcept_removal).

**Visual Studio 2017-Version 15.7:**

- Neuer Compilerschalter [/Qspectre ](build/reference/qspectre.md), um Speculative-Execution-Seitenkanalangriffe zu verringern. Weitere Informationen finden Sie unter [Spectre mitigations in MSVC (Spectre-Entschärfungen in MSVC)](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc/).
- Neue Diagnosewarnung für Spectre-Entschärfung. Weitere Informationen finden Sie unter [Spectre diagnostic in Visual Studio 2017 Version 15.7 Preview 4 (Spectre-Diagnose in Visual Studio 2017-Version 15.7, Vorschauversion 4)](https://blogs.msdn.microsoft.com/vcblog/2018/04/20/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/).
- Neuer Wert für/Zc, **/Zc:__cplusplus**: ermöglicht korrekte Berichterstattung für die Unterstützung des C++-Standards. Wenn der Schalter beispielsweise festgelegt ist und der Compiler sich im Modus /std:c ++17 befindet, wird der Wert auf **201703L** erweitert. Weitere Informationen finden Sie unter [MSVC now correctly reports __cplusplus (MSVC meldet jetzt ordnungsgemäß __cplusplus)](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/msvc-now-correctly-reports-__cplusplus/).

## <a name="c-standard-library-improvements"></a>Verbesserungen der C++-Standardbibliothek

- Kleinere Verbesserungen bei der Diagnose von `basic_string` `_ITERATOR_DEBUG_LEVEL != 0`. Das Auslösen einer IDL-Überprüfung in einer Zeichenfolgenmaschine meldet nun das bestimmte Verhalten, das die Überprüfung ausgelöst hat. Anstelle von „string iterator not dereferencable“ (Zeichenfolgeniterator nicht dereferenzierbar), erhalten Sie „cannot dereference string iterator because it is out of range (e.g. an end iterator)“ (Zeichenfolgeniterator ist nicht dereferenzierbar, da er sich außerhalb des Bereichs befindet (z.B. ein End-Iterator)).
- Leistungsverbesserung: `basic_string::find(char)`-Überladungen rufen nur einmal `traits::find` auf. Dies wurde zuvor als eine allgemeine Zeichenfolgensuche nach einer Zeichenfolge der Länge 1 implementiert.
- Leistungsverbesserung: `basic_string::operator==` überprüft nun die Größe der Zeichenfolge, bevor der Inhalt der Zeichenfolge verglichen wird.
- Leistungsverbesserung: die Kontrollkopplung in `basic_string`, die für den Compileroptimierer schwer zu analysieren war, wurde entfernt. Beachten Sie, dass bei kurzen Zeichenfolgen der Aufruf von `reserve` auch dann Kosten verursacht, wenn keine Arbeit erledigt wird.
- Wir haben \<any\>, \<string_view\>, `apply()` und `make_from_tuple()` hinzugefügt.
- `std::vector` wurde aufgrund der Korrektheit und Leistung überholt: Das Aliasing während der Einfügung und des Einbaus wird nun korrekt gehandhabt, so wie dies von Standard vorgesehen ist. Die starke Ausnahmegarantie wird nun bereitgestellt, wenn Standard dies durch `move_if_noexcept()` oder eine andere Logik erfordert. Die Einfügung bzw. der Einbau führen weniger Elementvorgänge durch.
- Die C++-Standardbibliothek vermeidet nun die Dereferenzierung von Fancy Pointern des Typs NULL.
- Es wurden \<optional\>, \<variant\>, `shared_ptr::weak_type`, und \<cstdalign\> hinzugefügt.
- C++14 `constexpr` wurde in `min(initializer_list)`, `max(initializer_list)` und `minmax(initializer_list)` und `min_element()`, `max_element()` und `minmax_element()` hinzugefügt.
- Verbesserte `weak_ptr::lock()`-Leistung.
- Der Bewegungszuweisungsoperator `std::promise`, der zuvor zum dauerhaften Blockieren von Code führen konnte, wurde korrigiert.
- Compilerfehler bei der impliziten Konvertierung von `atomic<T*>` in `T*` wurden behoben.
- `pointer_traits<Ptr>` erkennt jetzt ordnungsgemäß `Ptr::rebind<U>`.
- Ein fehlender `const`-Qualifizierer im `move_iterator`-Subtraktionsoperator wurde behoben.
- Die lautlose, ungültige Codegenerierung für zustandsbehaftete benutzerdefinierte Allokatoren, die `propagate_on_container_copy_assignment` und `propagate_on_container_move_assignment` anfordern, wurde korrigiert.
- `atomic<T>` toleriert nun den überladenen `operator&()`.
- Header der C++-Standardbibliothek vermeiden nun das Einschließen von Deklarationen für unnötige intrinsische Compilerfunktionen, um den Compilerdurchsatz zu erhöhen.
- Compilerdiagnosen für falsche `bind()`-Aufrufe wurden leicht verbessert.
- Die Leistung des Bewegungskonstruktors von `std::string` und `std::wstring` wurde um mehr als das Dreifache verbessert.

Eine vollständige Liste der Verbesserungen an der Standardbibliothek finden Sie unter [Standard Library Fixes In VS 2017 RTM](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/) (Korrekturen an der Standardbibliothek in VS 2017 RTM).

### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 Version 15.3

#### <a name="c17-features"></a>C++17-Features

Es wurden verschiedene weitere C++17-Features implementiert. Weitere Informationen finden Sie unter [Visual C++-Sprachkonformität](cpp-conformance-improvements-2017.md#improvements_153).

#### <a name="other-new-features"></a>Weitere neue Features

- P0602R0 wurde implementiert: „variant and optional should propagate copy/move triviality“.
- Die Standardbibliothek toleriert jetzt offiziell das Deaktivieren dynamischer RTTI über die Option [/GR-](build/reference/gr-enable-run-time-type-information.md). `dynamic_pointer_cast()` und `rethrow_if_nested()` erfordern grundsätzlich `dynamic_cast`. Die Standardbibliothek kennzeichnet sie also jetzt als `=delete` unter **/GR-**.
- Auch wenn dynamische RTTI über **/GR-** deaktiviert wurde, ist „statische RTTI“ (in Form von `typeid(SomeType)`) weiterhin verfügbar und unterstützt verschiedene Komponenten der Standardbibliothek. Die Standardbibliothek unterstützt über **/D\_HAS\_STATIC\_RTTI=0** jetzt auch die Deaktivierung der statischen RTTI. Beachten Sie, dass dadurch `std::any`, die Memberfunktionen `target()` und `target_type()` von `std::function` sowie die Friend-Memberfunktionen `get_deleter()` von `std::shared_ptr` und `std::weak_ptr` deaktiviert werden.

#### <a name="correctness-fixes-in-visual-studio-2017-version-153"></a>Fehlerbehebungen in Visual Studio 2017 Version 15.3

- Standardbibliothekscontainer binden nun ihre `max_size()` an `numeric_limits<difference_type>::max()`, anstatt `max()` an `size_type`. Dadurch wird sichergestellt, dass das Ergebnis von `distance()` in Iteratoren von diesem Container im Rückgabetyp von `distance()` darstellbar ist.
- Fehlende Spezialisierung wurde behoben: `auto_ptr<void>`.
- Die Algorithmen `for_each_n()`, `generate_n()` und `search_n()` konnten zuvor nicht kompiliert werden, wenn das length-Argument kein integraler Typ war. Jetzt wird versucht, nicht integrale Typen in den `difference_type` des Iterators zu konvertieren.
- `normal_distribution<float>` gibt in der Standardbibliothek beim Einschränken von „double“ auf „float“ keine Warnungen mehr aus.
- Einige `basic_string`-Vorgänge wurden korrigiert, bei denen bei Überprüfung der maximal zulässigen Überlaufgröße ein Vergleich mit `npos` anstatt mit `max_size()` erfolgte.
- `condition_variable::wait_for(lock, relative_time, predicate)` wartet in der Regel im Falle einer fälschlicherweise erfolgten Aktivierung die gesamte relative Zeit. Jetzt wird nur für ein einzelnes Intervall der relativen Zeit gewartet.
- `future::get()` macht jetzt das `future`-Objekt ungültig, so wie es der Standard erfordert.
- `iterator_traits<void *>` war zuvor ein harter Fehler, weil versucht wurde, `void&` zu formen. Es wird jetzt zu einer leeren Struktur, um die Verwendung von `iterator_traits` in "is iterator" SFINAE-Bedingungen zuzulassen.
- Einige von Clang **-Wsystem-headers**-Objekten gemeldete Warnungen wurden korrigiert.
- Die von „Clang **-Wmicrosoft-exception-spec**“ gemeldete Warnung „exception specification in declaration does not match previous declaration“ (die Ausnahmespezifikation in der Deklaration entspricht nicht der vorherigen Deklaration) wurde ebenfalls korrigiert.
- Von Clang und C1XX gemeldete mem-initializer-list-Reihenfolgewarnungen wurden ebenfalls korrigiert.
- Die unsortierten Container tauschten ihre Hasher oder Prädikate nicht, wenn die Container selbst getauscht wurden. Dies erfolgt jetzt.
- Viele swap-Vorgänge von Containern sind jetzt als `noexcept` markiert, da die Standardbibliothek niemals eine Ausnahme auslöst, wenn sie die nicht definierte Verhaltensbedingung „non-`propagate_on_container_swap` non-equal-allocator“ erkennt.
- Viele `vector<bool>`-Vorgänge sind jetzt als `noexcept` gekennzeichnet.
- Die Standardbibliothek erzwingt jetzt den Abgleich von `value_type` (im C++17-Modus) mit einem Escapehatch für die Abwahl.
- Einige Bedingungen wurden korrigiert, bei denen „self-range-insert“ in `basic_string` den Inhalt der Zeichenfolge durcheinandergebracht hat. (Hinweis: „self-range-insert“ in Vektoren ist im Standard immer noch nicht zulässig.)
- `basic_string::shrink_to_fit()` wird nicht länger vom `propagate_on_container_swap` der Zuweisung beeinträchtigt.
- `std::decay` verarbeitet jetzt abominable-Funktionstypen (also Funktionstypen mit cv- und/oder ref-Qualifizierer).
- include-Direktiven wurden geändert und verwenden jetzt die richtige Groß- und Kleinschreibung und Schrägstriche, was die Portierbarkeit verbessert.
- Warnung C4061 „enumerator '*enumerator*' in switch of enum '*enumeration*' is not explicitly handled by a case label“ (Enumerator 'enumerator' in der switch-Anweisung der Enumeration 'enumeration' wird von keiner case-Bezeichnung explizit behandelt) wurde korrigiert. Diese Warnung ist standardmäßig deaktiviert und wurde als Ausnahme der allgemeinen Richtlinie der Standardbibliothek für Warnungen korrigiert. (Die Standardbibliothek ist „**/W4** clean“, versucht jedoch nicht, „**/Wall** clean“ zu sein. Viele standardmäßig deaktivierte Warnungen verbrauchen viele Ressourcen und sind nicht für die regelmäßige Verwendung gedacht.)
- Verbesserte `std::list`-Debugüberprüfungen. Listeniteratoren überprüfen jetzt `operator->()`, und `list::unique()` markiert Iteratoren jetzt als ungültig.
- Die Metaprogrammierung von „uses-allocator“ wurde im `tuple` korrigiert.

#### <a name="performancethroughput-fixes"></a>Korrekturen für Leistung/Durchsatz

- Für Interaktionen mit `noexcept`, die ein Einbetten der `std::atomic`-Implementierung in Funktionen verhindert haben, die die strukturierte Ausnahmebehandlung verwenden, wurde eine Problemumgehung eingeführt.
- Die interne `_Deallocate()`-Funktion der Standardbibliothek wurde in kleinere Codeabschnitte optimiert, sodass sie jetzt inline an mehr Stellen eingebettet werden kann.
- `std::try_lock()` wurde geändert und verwendet jetzt Paketerweiterung anstelle von Rekursion.
- Der Algorithmus von `std::lock()` zum Verhindern von Deadlocks wurde verbessert und verwendet jetzt `lock()`-Vorgänge, anstatt alle `try_lock()` auf allen Sperren zu durchlaufen.
- Die Optimierung von benannten Rückgabewerten in `system_category::message()` wurde aktiviert.
- `conjunction` und `disjunction` instanziieren jetzt „N+1“-Typen anstatt „2N+2“-Typen.
- `std::function` instanziiert den Mechanismus für die Zuweisungsunterstützung nicht mehr für jedes aufrufbare Objekt mit Typlöschung. Dies erhöht den Durchsatz und reduziert die OBJ-Größe in Programmen, die viele verschiedene Lambdas an `std::function` übergeben.
- `allocator_traits<std::allocator>` enthält manuelle `std::allocator`-Inlinevorgänge und verringert die Codegröße in Code, der mit `std::allocator` nur über `allocator_traits` interagiert (dies gilt für den Großteil von Codes).
- Die minimale Zuweisungsschnittstelle von C++11 wird jetzt von der Standardbibliothek verarbeitet, die `allocator_traits` direkt aufruft, anstatt die Zuweisung in einer internen Klasse `_Wrap_alloc` zu umschließen. Dies reduziert den Umfang des Codes, der für die Unterstützung der Zuweisung generiert wird, verbessert in einigen Fällen die Möglichkeit des Optimierers, sich mit den Standardbibliothekscontainern auseinanderzusetzen, und verbessert das Debuggen (Sie sehen im Debugger jetzt Ihren Zuweisungstyp anstelle von `_Wrap_alloc<your_allocator_type>`).
- Die Metaprogrammierung für benutzerdefinierte `allocator::reference`-Elemente, die von Zuweisungen eigentlich nicht angepasst werden dürfen, wurde entfernt. (Durch Zuweisungen können Container originelle Zeiger verwenden, aber keine originellen Verweise.)
- Das Compiler-Front-End entpackt jetzt Debugiteratoren in reihenfolgebasierten for-Schleifen und verbessert so die Leistung von Debugbuilds.
- Der interne Reduzierungspfad von `basic_string` für `shrink_to_fit()` und `reserve()` befindet sich nicht mehr im Pfad für Neuzuweisungsvorgänge, wodurch der Codeumfang für alle mutierenden Member reduziert wird.
- Der interne Erweiterungspfad von `basic_string` befindet sich nicht mehr im Pfad von `shrink_to_fit()`.
- Mutierende Vorgänge von `basic_string` werden jetzt in nicht zuweisende schnelle Pfadfunktionen und zuweisende langsame Pfadfunktionen einbezogen, sodass allgemeine, nicht erneut zuweisende Funktionen wahrscheinlicher inline in aufrufende Funktionen eingebettet werden.
- Mutierende Vorgänge von `basic_string` konstruieren jetzt erneut zugewiesene Puffer im gewünschten Zustand, anstatt lokal die Größe zu ändern. Durch das Einfügen am Anfang einer Zeichenfolge wird der Inhalt hinter der Einfügung jetzt genau einmal (entweder nach unten oder in den neu zugewiesenen Puffer) anstatt zweimal im Fall der Neuzuweisung verschoben (in den neu zugewiesenen Puffer und dann nach unten).
- Vorgänge, die die C-Standardbibliothek in \<string\> aufrufen, speichern jetzt die Adresse von `errno`, um wiederholte Interaktionen mit TLS zu entfernen.
- Die Implementierung von `is_pointer` wurde vereinfacht.
- Die Änderung des funktionsbasierten Ausdrucks „SFINAE“ in `struct`- und `void_t`-basiert wurde abgeschlossen.
- Algorithmen der Standardbibliothek vermeiden jetzt postinkrementelle Iteratoren.
- Warnungen zu Abschneidungen beim Verwenden von 32-Bit-Zuweisungen in 64-Bit-Systemen wurden korrigiert.
- Die Zuweisung von `std::vector`-Verschiebungen erfolgt jetzt für Vorgänge, die weder der Zuweisung noch POCMA entsprechen, effizienter, indem nach Möglichkeit der Puffer wiederverwendet wird.

#### <a name="readability-and-other-improvements"></a>Verbesserungen der Lesbarkeit und andere Optimierungen

- Die Standardbibliothek verwendet jetzt „C++14 `constexpr`“ bedingungslos anstelle von bedingt definierten Makros.
- Die Standardbibliothek verwendet jetzt intern Aliasvorlagen.
- Die Standardbibliothek verwendet jetzt intern `nullptr` anstelle von `nullptr_t{}`. (Die interne Nutzung von NULL wurde gelöscht. Die interne Nutzung von „0-as-null“ wird nach und nach bereinigt.)
- Die Standardbibliothek verwendet jetzt intern `std::move()` anstelle der stilistisch fehlerhaften Verwendung von `std::forward()`.
- `static_assert(false, "message")` wurde in `#error message` geändert. Dies verbessert die Compilerdiagnose, da `#error` die Kompilierung sofort beendet.
- Die Standardbibliothek markiert Funktionen nicht mehr als `__declspec(dllimport)`. Für moderne Linkertechnologien ist dies nicht mehr erforderlich.
- SFINAE wurde in Standardvorlagenargumente extrahiert, wodurch der Code im Vergleich zu Rückgabetypen und Funktionsargumenttypen übersichtlicher wird.
- \<Zufällige\> Debugüberprüfungen verwenden jetzt die üblichen Mechanismen der Standardbibliothek anstelle der internen Funktion `_Rng_abort()`, die `fputs()` für **stderr** aufgerufen hat. Die Implementierung der Funktion wird zum Zweck der binären Kompatibilität beibehalten, wurde aber aus der nächsten binärinkompatiblen Version der Standardbibliothek entfernt.

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 Version 15.5

Mehrere Features der Standardbibliothek wurden in Übereinstimmung mit dem C++17-Standard hinzugefügt, als veraltet markiert oder entfernt. Weitere Informationen finden Sie unter [Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual Studio](cpp-conformance-improvements-2017.md#improvements_155).

#### <a name="new-experimental-features"></a>Neue experimentelle Features

- Experimentelle Unterstützung für die folgenden parallelen Algorithmen:
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- Die Signaturen für die folgenden parallelen Algorithmen werden hinzugefügt, aber zurzeit nicht parallelisiert. Die Profilerstellung zeigte keine Vorteile durch die Parallelisierung von Algorithmen, die Elemente nur verschieben oder permutieren:
  - `copy`
  - `copy_n`
  - `fill`
  - `fill_n`
  - `move`
  - `reverse`
  - `reverse_copy`
  - `rotate`
  - `rotate_copy`
  - `swap_ranges`

#### <a name="performance-fixes-and-improvements"></a>Fehlerbehebungen und Optimierungen der Leistung

- `basic_string<char16_t>` interagiert nun mit den gleichen Optimierungen von `memcmp` und `memcpy` sowie ähnlichen Optimierungen, die von `basic_string<wchar_t>` verwendet werden.
- Eine Einschränkung des Optimierers, die verhindert hat, dass Funktionszeiger durch unsere Arbeitsweise „Vermeiden von Kopierfunktionen“ in Visual Studio 2015 Update 3 inline dargestellt wurden, wurde umgangen, wodurch die Leistung von `lower_bound(iter, iter, function pointer)` wiederhergestellt wurde.
- Der Mehraufwand für die Überprüfung der Reihenfolge von Eingaben (`includes`, `set_difference`, `set_symmetric_difference` und `set_union`) des Iteratordebuggens wurde durch das Entpacken von Iteratoren vor der Überprüfung der Reihenfolge verringert.
- `std::inplace_merge` überspringt nun Elemente, die sich bereits in der richtigen Position befinden.
- Das Erstellen von `std::random_device` erstellt nicht länger ein `std::string`-Element bzw. zerstört es auch nicht mehr.
- Für `std::equal` und `std::partition` wurde ein Jump Threading-Optimierungsdurchlauf ausgeführt, der einen Iteratorvergleich erspart.
- Wenn `std::reverse` Zeiger auf trivial kopierbares `T` übergeben werden, erfolgt die Ausgabe nun an eine handgeschriebene vektorisierte Implementierung.
- `std::fill`, `std::equal` und `std::lexicographical_compare` wurden beigebracht, wie die Weiterleitung an `memset` und `memcmp` für `std::byte` und `gsl::byte` (sowie für andere char-ähnliche Enumerationen und Enumerationsklassen) funktioniert. Beachten Sie, dass die Weiterleitung für `std::copy` mithilfe von `is_trivially_copyable` erfolgt und deshalb keine Änderungen notwendig sind.
- Die Standardbibliothek enthält keine Destruktoren mehr mit leeren Klammern, deren einziges Verhalten darin bestand, Typen als nicht tribial zerstörbar zu definieren.

#### <a name="correctness-fixes-in-visual-studio-2017-version-155"></a>Fehlerbehebungen in Visual Studio 2017 Version 15.5

- `std::partition` ruft nun das Prädikat n Mal anstatt n+1 Mal auf, wie es der Standard verlangt.
- Versuche, Magic Statics in Version 15.3 zu vermeiden, wurden in Version 15.5 korrigiert.
- `std::atomic<T>` erfordert nicht mehr, dass `T` standardmäßig konstruierbar ist.
- Heapalgorithmen, die logarithmische Zeit erfordern, nehmen keine lineare Zeitassertion mehr vor, dass die Eingabe tatsächlich ein Heap ist, wenn Iteratordebuggen aktiviert ist.
- `__declspec(allocator)` wird jetzt nur noch für C1XX geschützt, um Warnungen von Clang zu verhindern, das diese declspec nicht versteht.
- `basic_string::npos` ist nun als Kompilierzeitkonstante verfügbar.
- `std::allocator` verarbeitet nun die Zuordnung von überalignierten Typen, also von Typen, deren Ausrichtung größer als `max_align_t` ist, im C++17-Modus ordnungsgemäß (wenn keine Deaktivierung durch **/Zc:alignedNew-** erfolgt).  Vektoren von Objekten mit 16- oder 32-Byte-Ausrichtung werden z.B. nun ordnungsgemäß für SSE- und AVX-Anweisungen ausgerichtet.

### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 Version 15.6

- \<memory_resource>
- Bibliotheksgrundlagen V1
- Löschen der polymorphic_allocator-Zuweisung
- Verbesserung der Klassenvorlagenargumentableitung

### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017-Version 15.7

- Unterstützung für parallele Algorithmen ist nicht mehr experimentell
- Eine neue Implementierung von \<filesystem>
- Elementare Zeichenfolgenkonvertierungen (partiell)
- std::launder()
- std::byte
- hypot(x,y,z)
- Vermeiden unnötigen Verfalls
- Mathematische spezielle Funktionen
- constexpr char_traits
- Herleitungsregelwerk für STL

Weitere Informationen finden Sie unter [Visual C++-Sprachkonformität](visual-cpp-language-conformance.md).

## <a name="other-libraries"></a>Weitere Bibliotheken

### <a name="open-source-library-support"></a>Unterstützung für Open-Source-Bibliotheken

**Vcpkg** ist ein Open-Source-Befehlszeilentool, das den Prozess des Beziehens und Erstellens von statischen C++-Open-Source Bibliotheken und DLLs in Visual Studio sehr stark vereinfacht. Weitere Informationen finden Sie unter [vcpkg: A Package Manager for C++ (vcpkg: Ein Paket-Manager für C++)](vcpkg.md).

**Visual Studio 2017 Version 15.5**:

### <a name="cpprest-sdk-290"></a>C++ REST SDK 2.9.0

Das C++ REST SDK, eine plattformübergreifende Web-API für C++, wurde auf Version 2.9.0 aktualisiert. Weitere Informationen finden Sie im Blogbeitrag [CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

- Weitere Korrekturen an der Übereinstimmung bei der Suche nach Namen
- Vorhandene Bewegungskonstruktoren und Bewegungszuweisungsoperatoren werden jetzt ordnungsgemäß als nicht auslösend markiert.
- Die gültige Warnung C4640 zur threadsicheren Initialisierung von lokalen statischen Variablen in „atlstr.h“ wird nicht mehr unterdrückt.
- Die threadsichere Initialisierung lokaler statischer Variablen wurde bei [Verwendung von ATL UND Erstellen einer DLL] im XP-Toolset automatisch deaktiviert. Dies ist nun nicht mehr der Fall. Wenn Sie die threadsichere Initialisierung ausschalten möchten, können Sie **/Zc:threadSafeInit-** in Ihren Projekteinstellungen hinzufügen.

### <a name="visual-c-runtime"></a>Visual C++ Runtime

- Neuer Header „cfguard.h“ für Ablaufsteuerungsschutz-Symbole.

## <a name="c-ide"></a>C++-IDE

- Die Leistung bei Konfigurationsänderungen ist jetzt für native C++-Projekte besser und für C++-/CLI-Projekte viel besser. Wenn eine Projektmappenkonfiguration zum ersten Mal aktiviert wird, ist sie jetzt schneller, und alle nachfolgenden Aktivierungen dieser Projektmappenkonfiguration erfolgen fast unmittelbar.

**Visual Studio 2017 Version 15.3**:

- Verschiedene Projekt- und Code-Assistenten wurden im Signaturdialogstil umgeschrieben.
- **Klasse hinzufügen** startet den Assistenten zum Hinzufügen von Klassen nun direkt. Alle anderen Elemente, die hier zuvor verfügbar waren, finden Sie nun unter **Hinzufügen > Neues Element**.
- Win32-Projekte sind nun im Dialogfeld **Neues Projekt** in der **Windows Desktop-Kategorie** zu finden.
- Die **Windows-Konsolen**- und **Desktopanwendungsvorlagen** erstellen die Projekte nun, ohne einen Assistenten anzuzeigen. Es gibt einen neuen **Windows Desktop-Assistenten** in der gleichen Kategorie, der die gleichen Optionen wie der alte Assistent für die **Win32-Konsolenanwendung** anzeigt.

**Visual Studio 2017 Version 15.5**:

Mehrere Vorgänge in C++, die die IntelliSense-Engine für Refactoring und Codenavigation verwenden, werden viel schneller ausgeführt. Die folgenden Angaben basieren auf der Visual Studio Chromium-Lösung mit 3.500 Projekten:

|||
|-|-|
|Feature|Leistungssteigerung|
|Umbenennen|5,3-fach|
|Signatur ändern |4,5-fach|
|Alle Verweise suchen|4,7-fach|

C++ unterstützt jetzt STRG+Klick-**GoTo-Definition**, was die Navigation mit der Maus zu Definitionen vereinfacht. Die Strukturvisualisierung aus dem Productivity Power Tools-Paket ist nun standardmäßig auch im Produkt enthalten.

## <a name="intellisense"></a>IntelliSense

- Die neue, auf SQLite basierende Datenbank-Engine wird jetzt standardmäßig verwendet. Dadurch werden Datenbankoperationen wie **Gehe zu Definition** und **Alle Verweise suchen** beschleunigt, und die Zeit für die erstmalige Analyse einer Projektmappe verkürzt sich erheblich. Die Einstellung wurde nach **Extras > Optionen > Texteditor > C/C++ > Erweitert** verschoben (sie befand sich bisher unter ...„C/C++“ > „Experimentell“).

- Wir haben die IntelliSense-Leistung für Projekte und Dateien verbessert, die keine vorkompilierten Header verwenden. Ein automatisch vorkompilierter Header wird für Header in der aktuellen Datei erstellt.

- Wir haben die Fehlerfilterung und Hilfe für IntelliSense-Fehler in der Fehlerliste hinzugefügt. Das Klicken auf die Fehlerspalte ermöglicht jetzt die Filterung. Durch Klicken auf die einzelnen Fehler oder durch Drücken von F1 wird eine Onlinesuche nach der Fehlermeldung gestartet.

  ![Fehlerliste](media/ErrorList1.png "Fehlerliste")

  ![Fehlerliste gefiltert](media/ErrorList2.png "Fehlerliste gefiltert")

- Die Möglichkeit zum Filtern von Elementen der Memberliste nach Typ wurde hinzugefügt.

  ![Filterung der Memberliste](media/mlfiltering.png "Filterung der Memberliste")

- Eine neue experimentelle, vorhersehbare IntelliSense-Funktion, die das kontextbewusste Filtern in der Memberliste bereitstellt, wurde hinzugefügt. Weitere Informationen finden Sie im Blogpost [C++ IntelliSense Improvements – Predictive IntelliSense & Filtering (Verbesserungen in C++-IntelliSense: Predictive IntelliSense und Filtern)](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)
- **Alle Verweise suchen** (UMSCHALT+F12) ermöglicht nun eine einfachere Navigation, auch in komplexen Codebasen. Das Feature bietet eine erweiterte Gruppierung, Filterung, Sortierung, Suche in Ergebnissen und (für einige Sprachen) eine Einfärbung, damit Sie Ihre Verweise umfassend verstehen können. Für C++ enthält die neue Benutzeroberfläche Informationen dazu, ob Informationen aus einer Variablen gelesen oder in eine Variable geschrieben werden.
- Die Punkt-zu-Pfeil-Funktion von IntelliSense wurde aus „experimentell“ in „erweitert“ verschoben und ist nun standardmäßig aktiviert. Die Editor-Funktionen **Erweiterungsbereiche** und **Erweiterungsrangfolge** wurden auch von „experimentell“ zu „erweitert“ verschoben.
- Die experimentellen Refactoringfeatures **Signatur ändern** und **Funktion extrahieren** sind nun standardmäßig verfügbar.
- Das neue experimentelle Feature „Schnelleres Laden von Projekten“ für C++-Projekte wurde aktiviert. Wenn Sie das nächste Mal ein C++-Projekt öffnen, wird es schneller geladen und das darauffolgende Mal wird es richtig schnell geladen!
- Einige dieser Features sind auch in anderen Sprachen gängig, während einige C++-spezifisch sind. Weitere Informationen zu diesen neuen Features finden Sie im Blogbeitrag [Announcing Visual Studio "15" (Ankündigung von Visual Studio 2017)](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/).

**Visual Studio 2017-Version 15.7**: Unterstützung für ClangFormat hinzugefügt. Weitere Informationen finden Sie im Blogbeitrag [ClangFormat Support in Visual Studio 2017 (Unterstützung für ClangFormat in Visual Studio 2017)](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>Nicht-MSBuild-Projekte mit „Ordner öffnen“

In Visual Studio 2017 wurde das Feature **Ordner öffnen** eingeführt, das Ihnen das Programmieren, Erstellen von Builds und Debuggen in einem Ordner mit Quellcode ermöglicht, ohne dass Projektmappen oder Projekte erstellt werden müssen. Dadurch wird der Einstieg in Visual Studio wesentlich einfacher, selbst wenn Ihr Projekt kein auf MSBuild basierendes Projekt ist. Mit **Ordner öffnen** erhalten Sie Zugang zu den Funktionen zum Verstehen, Bearbeiten, Erstellen und Debuggen von Code, die Visual Studio bereits für MSBuild-Projekte bietet. Weitere Informationen finden Sie unter [Ordner öffnen-Projekte in Visual C++](ide/non-msbuild-projects.md).

- Verbesserungen in der Benutzeroberfläche „Ordner öffnen“. Sie können die Oberfläche über diese JSON-Dateien anpassen:
  - CppProperties.json zum Anpassen des IntelliSense- und Browsererlebnisses.
  - Tasks.json zum Anpassen der Buildschritte.
  - Launch.json zum Anpassen des Debugvorgangs.

**Visual Studio 2017 Version 15.3**:

- Die Unterstützung für alternative Compiler und Buildumgebungen wie MinGW und Cygwin wurde verbessert. Weitere Informationen finden Sie unter [Using MinGW and Cygwin with Visual C++ and Open Folder](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/) (Verwenden von MinGW und Cygwin mit Visual C++ und „Ordner öffnen“).
- Unterstützung für das Definieren von globalen und konfigurationsspezifischen Umgebungsvariablen in „CppProperties.json“ und „CMakeSettings.json“ wurde hinzugefügt. Diese Umgebungsvariablen können von in „launch.vs.json“ definierten Debugkonfigurationen und von Aufgaben in „tasks.vs.json“ verwendet werden. Weitere Informationen finden Sie unter [Anpassen Ihrer Umgebung mit Visual C++ und „Ordner öffnen“](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/customizing-your-environment-with-visual-c-and-open-folder/).
- Unterstützung für den Ninja-Generator von CMake wurde verbessert, einschließlich der Möglichkeit, ganz einfach 64-Bit-Plattformen als Ziel zu verwenden.

## <a name="cmake-support-via-open-folder"></a>Unterstützung von CMake über „Ordner öffnen“

Visual Studio 2017 führt die Unterstützung für die Verwendung von CMake-Projekten ohne Konvertierung in MSBuild-Projektdateien (.vcxproj) ein. Weitere Informationen finden Sie unter [CMake-Projekte in Visual C++](ide/cmake-tools-for-visual-cpp.md). Durch Öffnen von CMake-Projekten mit **Ordner öffnen** wird die Umgebung für die Bearbeitung, Erstellung und das Debuggen von C++ automatisch konfiguriert.

- C++-IntelliSense funktioniert, ohne dass Sie eine „CppProperties.json“-Datei im Stammordner erstellen müssen. Darüber hinaus haben wir ein neues Dropdownmenü hinzugefügt, sodass Benutzer einfach zwischen von CMake - und CppProperties.json-Dateien bereitgestellten Konfigurationen wechseln können.

- Weitere Konfigurationen werden über eine Datei „CMakeSettings.json“ unterstützt, die sich im gleichen Ordner wie die Datei „CMakeLists.txt“ befindet.

  ![„Ordner öffnen“ von Cmake](media/cmake_cpp.png "„Ordner öffnen“ von Cmake")

**Visual Studio 2017 Version 15.3**: Unterstützung für den Ninja-Generator von CMake hinzugefügt. 

**Visual Studio 2017 Version 15.5**: Unterstützung für das Importieren von vorhandenen CMake-Caches wurde hinzugefügt. 

**Visual Studio 2017-Version 15.7:** Unterstützung für CMake 3.11, die Codeanalyse in CMake-Projekten, die Ansicht „Ziele“ im Projektmappen-Explorer, die Optionen zur Cachegenerierung und die Kompilierung von Einzeldateien hinzugefügt. Weitere Informationen finden Sie im Blogbeitrag [CMake Support in Visual Studio – Targets View, Single File Compilation, and Cache Generation Settings (CMake-Unterstützung in Visual Studio: Ansicht „Ziele“, Kompilierung von Einzeldateien und Einstellungen für Cachegenerierung)](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) und [CMake-Projekte in Visual C++](ide/cmake-tools-for-visual-cpp.md).

## <a name="windows-desktop-development-with-c"></a>Windows Desktop-Entwicklung mit C++

Die Installationsoberfläche ermöglicht bei der Installation der ursprünglichen C++-Arbeitsauslastung jetzt eine feinere Abstimmung. Wir haben auswählbare Komponenten hinzugefügt, sodass Sie nur die Tools installieren können, die Sie benötigen.  Beachten Sie, dass die angegebenen Installationsgrößen für die im Installationsprogramm aufgeführten Komponenten nicht genau sind und die Gesamtgröße unterschätzen.

Wenn Sie Win32-Projekte erfolgreich in der C++-Desktoparbeitsauslastung erstellen möchten, müssen Sie ein Toolset und ein Windows SDK installieren. Zum Installieren der empfohlenen (ausgewählten) Komponenten benötigen Sie **VC++ 2017 c141 Toolset (x86, x64)** und **Windows 10 SDK (10.0.nnnnn)**. Sollten die nötigen Tools nicht installiert sein, können Projekte nicht erfolgreich erstellt werden. Außerdem wird der Assistent nicht mehr reagieren.

**Visual Studio 2017 Version 15.5**:

Die Visual C++ Build-Tools (zuvor als eigenständiges Produkt verfügbar) sind jetzt als Workload im Visual Studio-Installer enthalten. Diese Workload installiert nur die Tools, die zum Erstellen von C++-Projekten ohne Installation der Visual Studio-IDE erforderlich sind. Die Toolsets v140 und v141 sind beide enthalten. Das v141-Toolset enthält die neuesten Verbesserungen in Visual Studio 2017 Version 15.5. Weitere Informationen finden Sie unter [Visual Studio Build Tools enthalten nun die MSVC-Toolsets VS2017 und VS2015](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/).

## <a name="linux-development-with-c"></a>Linux-Entwicklung mit C++

Die beliebte Erweiterung [Visual C++ für Linux-Entwicklung](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) ist nun Bestandteil von Visual Studio. Diese Installation bietet alles, was Sie zum Entwickeln und Debuggen von C++-Anwendungen in einer Linux-Umgebung benötigen.

**Visual Studio 2017 (Version 15.2)**:

Verbesserungen für plattformübergreifende gemeinsame Codenutzung und Typvisualisierung. Weitere Informationen finden Sie unter [Linux C++ improvements for cross-platform code sharing and type visualization](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/) (Linux C++ – Verbesserungen für plattformübergreifende gemeinsame Codenutzung und Typvisualisierung).

**Visual Studio 2017 Version 15.5**:

- Die Linux-Workload hat Unterstützung für **rsync** als Alternative zu **sftp** hinzugefügt, um Dateien auf Linux-Remotecomputern zu synchronisieren.
- Unterstützung für Kreuzkompilierung für ARM-Mikrocontroller wurde hinzugefügt. Um dies in der Installation zu aktivieren, wählen Sie **Linux-Entwicklung mit der C++-Workload** und dann die Option für **Eingebettete und IoT-Entwicklung** aus. Dadurch werden die ARM GCC-Kreuzkompilierungstools und Make Ihrer Installation hinzugefügt. Weitere Informationen finden Sie unter [ARM GCC-Kreuzkompilierung in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2017/10/23/arm-gcc-cross-compilation-in-visual-studio/).
- Unterstützung für CMake wurde hinzugefügt. Sie können nun an Ihrer bestehenden CMake-Codebasis arbeiten, ohne sie in ein Visual Studio-Projekt konvertieren zu müssen. Weitere Informationen finden Sie unter [Konfigurieren eines Linux CMake-Projekts](linux/cmake-linux-project.md).
- Unterstützung für das Ausführen von Remotetasks wurde hinzugefügt. Mit dieser Funktion können Sie jeden Befehl auf einem Remotesystem ausführen, das im Verbindungs-Manager von Visual Studio definiert ist. Remotetasks bieten auch die Möglichkeit zum Kopieren von Dateien auf das Remotesystem.
Weitere Informationen finden Sie unter [Konfigurieren eines Linux CMake-Projekts](linux/cmake-linux-project.md).

**Visual Studio 2017-Version 15.7:**

- Verschiedene Verbesserungen für Linux-Workload-Szenarios. Weitere Informationen finden Sie unter [Linux C++ Workload improvements to the Project System, Linux Console Window, rsync and Attach to Process (Verbesserungen der Linux-C++-Workload für das Projektsystem, die Linux-Konsole, Windows, rsync und „An den Prozess anhängen“)](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- IntelliSense für Header in Linux-Remoteverbindungen. Weitere Informationen finden Sie unter [IntelliSense for Remote Linux Headers (IntelliSense für Linux-Remoteheaders)](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/intellisense-for-remote-linux-headers/) und [Konfigurieren eines Linux-CMake-Projekts](linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>Spieleentwicklung mit C++

Verwenden Sie die volle Leistung von C++, um professionelle Spiele zu erstellen, die von DirectX oder Cocos2d unterstützt werden.

## <a name="mobile-development-with-c-android-and-ios"></a>Mobile Entwicklung mit C++ (Android und iOS)

Sie können nun mithilfe von Visual Studio mobile Apps erstellen und debuggen, die auf Android und iOS ausgerichtet sind.

## <a name="universal-windows-apps"></a>Universelle Windows-Apps

C++ wird als optionale Komponente für die Arbeitsauslastung der Universellen Windows-App bereitgestellt.  Upgrades von C++-Projekten müssen zurzeit manuell ausgeführt werden. Wenn Sie ein auf UWP-Projekt mit dem Ziel v140 in Visual Studio 2017 öffnen, müssen Sie das v141-Plattformtoolset auf den Projekteigenschaftenseiten auswählen, wenn Visual Studio 2015 nicht installiert ist.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>Neue Optionen für C++ auf der universellen Windows-Plattform (UWP)
Jetzt stehen Ihnen neue Optionen für das Schreiben und Packen von C++-Anwendungen für die universelle Windows-Plattform und den Microsoft Store zur Verfügung: Sie können die Desktop Bridge-Infrastruktur zum Packen Ihrer vorhandenen Desktopanwendung oder das COM-Objekt für die Bereitstellung über den Microsoft Store oder mittels Querladen über Ihre vorhandenen Kanäle nutzen. Mit den neuen Funktionen in Windows 10 können Sie Ihre Desktopanwendung auf unterschiedliche Weise um die Funktionalität der universellen Windows-Plattform (UWP) erweitern. Weitere Informationen finden Sie unter [Desktop Bridge](/windows/uwp/porting/desktop-to-uwp-root).

**Visual Studio 2017, Version 15.5**  
Eine Projektvorlage **Paketerstellungsprojekt für Windows-Anwendungen** wurde hinzugefügt, die die Paketerstellung von Desktopanwendungen mithilfe von Desktop Bridge unterstützt. Sie ist unter **Datei > Neu > Projekt > Installiert > Visual C++ > Universelle Windows-Plattform** verfügbar. Weitere Informationen finden Sie unter [Packen einer App mit Visual Studio (Desktop Bridge)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

Beim Schreiben von neuem Code können Sie nun C++/WinRT verwenden. Dies ist eine C++-Standardsprachprojektion für Windows-Runtime (WinRT), die nur in Headerdateien implementiert wird. Mit ihr können Sie Windows-Runtime-APIs mit jedem C+-Compiler erstellen und nutzen, der mit Standards kompatibel ist. C++/WinRT wurde dafür konzipiert, C++-Entwicklern erstklassigen Zugriff auf die moderne Windows-API zur Verfügung zu stellen. Weitere Informationen finden Sie im Blogbeitrag [C++/WinRT Available on GitHub](https://moderncpp.com/).

Ab [Build 17025 der Windows SDK Insider Preview](https://blogs.windows.com/buildingapps/2017/11/01/windows-10-sdk-preview-build-17025/#ryPH3zAy6yk2cIRX.97) ist C++/WinRT im Windows SDK enthalten. Weitere Informationen finden Sie unter [C++/WinRT ist jetzt im Windows SDK enthalten](https://blogs.msdn.microsoft.com/vcblog/2017/11/01/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2-Plattformtoolset

Das Clang/C2-Toolset, das im Lieferumfang von Visual Studio 2017 enthalten ist, unterstützt jetzt den Parameter **/bigobj**, der für das Erstellen großer Projekte entscheidend ist. Es umfasst außerdem eine Reihe wichtiger Programmfehlerbehebungen, sowohl im Front-End als auch im Back-End des Compilers.

## <a name="c-code-analysis"></a>C++-Codeanalyse

Visual Studio liefert nun die C++-Kernprüfungen zum Erzwingen der [C++-Kernrichtlinien](https://github.com/isocpp/CppCoreGuidelines). Aktivieren Sie die Prüfungen einfach auf der Seite **Code Analysis Extensions** (Codeanalyseerweiterungen) auf den Eigenschaftenseiten des Projekts, und die Erweiterungen sind enthalten, wenn Sie die Codeanalyse ausführen. Weitere Informationen finden Sie unter [Verwenden der C++-Core-Richtlinienprüfungen](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck-Eigenschaftenseite")

**Visual Studio 2017 Version 15.3**: Unterstützung für Regeln in Bezug auf die Ressourcenverwaltung hinzugefügt.

**Visual Studio 2017 Version 15.5**: Neue C++ Core Guidelines überprüfen intelligente Zeiger auf Richtigkeit, prüfen die richtige Verwendung von globalen Initialisierern und kennzeichnen die Verwendungen von Konstrukten wie `goto` sowie fehlerhafte Typumwandlungen.

Einige Warnnummern, die in Version 15.3 vorhanden waren, sind in Version 15.5 nicht mehr verfügbar. Diese Warnungen wurden durch genauere Überprüfungen ersetzt.

**Visual Studio 2017-Version 15.6:**  
Unterstützung für die Analyse von Einzeldateien hinzugefügt und Verbesserungen der Laufzeitleistung der Analyse vorgenommen. Weitere Informationen finden Sie unter [C++ Static Analysis Improvements for Visual Studio 2017 15.6 Preview 2 (Verbesserungen an der statischen C++-Analyse für Visual Studio 2017-Version 15.6, Vorschauversion 2)](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

**Visual Studio 2017-Version 15.7:**  

- Unterstützung für [/analyze:ruleset](build/reference/analyze-code-analysis.md) hinzugefügt. So können Sie angeben, welche Codeanalyseregeln ausgeführt werden sollen.
- Unterstützung für zusätzliche C++ Core Guidelines-Regeln hinzugefügt.  Weitere Informationen finden Sie unter [Verwenden der C++-Core-Richtlinienprüfungen](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Unittest

**Visual Studio 2017 Version 15.5**:

Google Test Adapter und Boost.Test-Adapter sind jetzt als Komponenten der Workload **Desktopentwicklung mit C++** verfügbar und werden in **Test Explorer** integriert. CTest-Unterstützung wurde für Cmake-Projekte hinzugefügt (unter Verwendung von „Ordner öffnen“), obwohl die vollständige Integration in **Test Explorer** noch nicht verfügbar ist. Weitere Informationen finden unter [Erstellen von Komponententests für C/C++](/visualstudio/test/writing-unit-tests-for-c-cpp).

**Visual Studio 2017-Version 15.6:**

- Unterstützung für dynamische Boost.Test-Bibliotheksunterstützung hinzugefügt.
- Eine Boost.Test-Elementvorlage steht jetzt in der IDE zur Verfügung.

Weitere Informationen finden Sie unter [Boost.Test Unit Testing: Dynamic Library support and New Item Template (Boost.Test-Unittests: dynamische Bibliotheksunterstützung und neue Elementvorlage)](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/boost-test-unit-testing-dynamic-library-support-and-new-item-template/). 

**Visual Studio 2017-Version 15.7:**

Unterstützung für [CodeLens](https://docs.microsoft.com/en-us/visualstudio/ide/find-code-changes-and-other-history-with-codelens) für C++-Komponententestprojekte hinzugefügt. Weitere Informationen finden Sie unter [Announcing CodeLens for C++ Unit Testing (Ankündigung: CodeLens für C++-Unittests)](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/announcing-codelens-for-c-unit-testing/).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio-Grafikdiagnose

Die Grafikdiagnose von Visual Studio umfasst eine Reihe von Tools zum Aufzeichnen und Analysieren von Rendering- und Leistungsproblemen in Direct3D-Apps. Die Features der Grafikdiagnose können für Apps verwendet werden, die lokal auf Ihrem Windows-PC, in einem Windows-Geräteemulator oder auf einem Remotecomputer oder-gerät ausgeführt werden.

- **Ein- und Ausgabe von Vertex- und Geometrieshadern:** Die Möglichkeit der Anzeige der Ein- und Ausgabe von Vertex- und Geometrieshadern war eines der am häufigsten gewünschten Features, das nun in den Tools unterstützt wird. Wählen Sie einfach die VS- oder GS-Phase in der Ansicht „Pipelinestufen“, um mit dem Untersuchen der Ein- und Ausgabe in der nachstehenden Tabelle zu beginnen.

  ![Ein-/Ausgabe für Shader](media/io-shaders.png)

- **Suchen und Filtern in der Objekttabelle:** Bietet eine schnelle und einfache Möglichkeit, die gesuchten Ressourcen zu finden.

  ![Suchen](media/search.png)

- **Ressourcenverlauf:** Diese neue Ansicht bietet eine optimierte Möglichkeit der Ansicht des gesamten Änderungsverlaufs einer Ressource gemäß ihrer Verwendung während der Wiedergabe eines aufgezeichneten Frames. Um den Verlauf für jede Ressource aufzurufen, klicken Sie einfach auf das Uhrsymbol neben jeden Ressourcenlink.

  ![Ressourcenverlauf](media/resource-history.png)

  Hiermit wird das Toolfenster **Ressourcenverlauf** angezeigt, in dem sich der Änderungsverlauf der Ressource befindet.

  ![Ressourcenverlaufsänderung](media/resource-history-change.png)

  Wenn Ihr Frame bei aktivierter vollständiger Aufruflistenerfassung erfasst wurde (**Visual Studio > Extras > Optionen** unter **Grafikdiagnose**), kann der Kontext jedes einzelnen Änderungsereignisses schnell abgeleitet und innerhalb Ihres Visual Studio-Projekts überprüft werden.

- **API-Statistiken:** Eine allgemeine Zusammenfassung der API-Verwendung in Ihrem Frame. Dies kann beim Ermitteln von Aufrufen nützlich sein, von denen Sie nicht wissen, dass sie erfolgen, oder von Aufrufen, die zu oft erfolgen. Dieses Fenster steht über **Ansicht > API Statistiken** in der Visual Studio-Grafikanalyse zur Verfügung.

  ![API-Statistiken](media/api-stats.png)

- **Speicherstatistiken:** Zeigt, wie viel Arbeitsspeicher der Treiber für die Ressourcen reserviert, die Sie im Frame erstellen. Dieses Fenster steht über **Ansicht > Speicherstatistiken** in der **Visual Studio-Grafikanalyse** zur Verfügung. Daten können zum Anzeigen in einer Tabelle in eine CSV-Datei kopiert werden, indem mit der rechten Maustaste geklickt und dann **Alles kopieren** ausgewählt wird.

  ![Speicherstatistiken](media/memory-stats.png)

- **Frame-Überprüfung:** Die neue Liste mit Fehlern und Warnungen bietet eine einfache Möglichkeit der Navigation zu Ihrer Ereignisliste basierend auf potenziellen Problemen, die auf Direct3D-Debugebene erkannt wurden. Klicken Sie zum Öffnen des Fensters in der Visual Studio-Grafikanalyse auf **Ansicht > Frame-Überprüfung**. Klicken Sie dann auf **Überprüfung ausführen**, um die Analyse zu starten. Je nach Komplexität des Frames kann dieser Vorgang mehrere Minuten dauern.

  ![Frame-Überprüfung](media/frame-validation.png)

- **Frame-Analyse für D3D12:** Verwenden Sie die Frame-Analyse zum Analysieren der Leistung von Zeichnen-Befehlen mit „Was-wäre-wenn“-Experimenten. Wechseln Sie zur Registerkarte „Frame-Analyse“, und führen Sie Analysen aus, um den Bericht anzuzeigen. Weitere Informationen bietet das Video [GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool).

  ![Frame-Analyse](media/frame-analysis.png)

- **Verbesserungen der GPU-Nutzung:** Öffnen Sie Ablaufverfolgungen, die über den Visual Studio-Profiler für GPU-Nutzung mit entweder dem Tool „GPU-Ansicht“ oder Windows Performance Analyzer (WPA) erstellt wurden, um eine detailliertere Analyse zu erhalten. Wenn das Windows Performance Toolkit installiert ist, sind rechts unten in der Sitzungsübersicht zwei Links vorhanden: einer für WPA und einer für die GUP-Ansicht.

  ![GPU-Nutzung](media/gpu-usage.png)

  Über diesen Link in der GPU-Ansicht geöffnete Ablaufverfolgungen unterstützen das synchronisierte Zoomen und Schwenken auf der Zeitachse zwischen Visual Studio und GPU-Ansicht. Ein Kontrollkästchen in Visual Studio dient zum Steuern, ob die Synchronisierung aktiviert ist oder nicht.

  ![GPU-Ansicht](media/gpu-view.png)
