---
title: C-C++ /Projekteigenschaften (Visual Studio)
ms.date: 07/18/2019
ms.topic: article
ms.assetid: 16375038-4917-4bd0-9a2a-26343c1708b7
ms.openlocfilehash: 2f7fe025eb69fc1977713c638eef0742074bd9fb
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927746"
---
# <a name="cc-property-pages"></a>C/C++ Eigenschaften Seiten

Die folgenden Eigenschaften Seiten finden Sie unter **Projekt** > **Eigenschaften** > **Konfigurations Eigenschaften** > **C/C++** :

## <a name="cc-general-properties"></a>C/C++ allgemeine Eigenschaften

### <a name="additional-include-directories"></a>Zusätzliche Includeverzeichnisse

Gibt mindestens ein Verzeichnis an, das dem include-Pfad hinzugefügt werden soll. Verwenden Sie Semikolons als Trennzeichen, wenn mehrere Verzeichnisse vorhanden sind. Legt [/I (Zusätzliche Includeverzeichnisse)](i-additional-include-directories.md)fest.

### <a name="additional-using-directories"></a>Zusätzliche #using Verzeichnisse

Gibt ein oder mehrere Verzeichnisse an (getrennte Verzeichnisnamen mit einem Semikolon), die durchsucht werden sollen, um Namen aufzulösen, die an eine #using Direktive weitergegeben Legt [/AI](ai-specify-metadata-directories.md)fest.

### <a name="debug-information-format"></a>Debuginformationsformat

Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden.  Hierfür sind kompatible Linker-Einstellungen erforderlich. Legt [/Z7,/Zi,/Zi (Debuginformationsformat)](z7-zi-zi-debug-information-format.md)fest.

**Optionen**

- **Keine**: Generiert keine Debuginformationen, sodass die Kompilierung ggf. schneller erfolgt.
- **C7-kompatibel** : Wählen Sie den Typ der Debuginformationen aus, der für Ihr Programm erstellt wurde, und ob diese Informationen in Objektdateien (obj) oder in einer Programmdatenbank (PDB) gespeichert werden.
- **Programmdatenbank** : erstellt eine Programmdatenbank (PDB), die Typinformationen und symbolische Debuginformationen für die Verwendung mit dem Debugger enthält. Zu den symbolischen Debuginformationen gehören die Namen und Typen von Variablen sowie Funktionen und Zeilennummern.
- **Programmdatenbank zum Bearbeiten und Fortfahren** : erstellt eine Programmdatenbank, wie oben beschrieben, in einem Format, das die Funktion " [Bearbeiten und Fortfahren](/visualstudio/debugger/edit-and-continue) " unterstützt.

### <a name="support-just-my-code-debugging"></a>Unterstützung nur eigenen Code Debugging

Fügt unterstützenden Code zum Aktivieren [nur eigenen Code](/visualstudio/debugger/just-my-code) Debuggens in dieser Kompilierungseinheit hinzu. Legt [/JMC](jmc.md)fest.

### <a name="common-language-runtime-support"></a>Common Language Runtime-Unterstützung

Verwenden Sie den .net-Lauf Zeit Dienst.  Dieser Switch ist mit anderen Switches nicht kompatibel. Ausführliche Informationen finden Sie in der Dokumentation zur [/CLR](clr-common-language-runtime-compilation.md) -Familie von Switches.

**Optionen**

- **Keine Common Language Runtime-Unterstützung** -keine Common Language Runtime-Unterstützung
- **Common Language Runtime-Unterstützung** : erstellt Metadaten für Ihre Anwendung, die von anderen CLR-Anwendungen genutzt werden können, und ermöglicht der Anwendung die Nutzung von Typen und Daten in den Metadaten anderer CLR-Komponenten.
- **Pure MSIL Common Language Runtime-Unterstützung** : erzeugt eine nur- [MSIL](/dotnet/standard/managed-code)-Ausgabedatei ohne nativen ausführbaren Code, obwohl Sie Native Typen enthalten kann, die in MSIL kompiliert werden.
- **Sichere MSIL Common Language Runtime-Unterstützung** : erzeugt einen reinen MSIL-Code (kein System eigener ausführbarer Code) und eine überprüfbare Ausgabedatei.

### <a name="consume-windows-runtime-extension"></a>Windows-Runtime Erweiterung verbrauchen

Verwendet die Windows-Lauf Zeit Sprachen-Erweiterungen. Legt [/ZW](zw-windows-runtime-compilation.md)fest.

### <a name="suppress-startup-banner"></a>Startbanner unterdrücken

Unterdrückt die Anzeige des Anmelde Banners, wenn der Compiler startet und während der Kompilierung Informationsmeldungen anzeigt.

### <a name="warning-level"></a>Warnstufe

Wählen Sie aus, wie streng der Compiler bei Codefehlern sein soll. Legt [/W0-/W4](compiler-option-warning-level.md)fest.

**Optionen**

- **Alle Warnungen** deaktivieren: auf Ebene 0 werden alle Warnungen deaktiviert.
- **Level1** -Level 1 zeigt schwerwiegende Warnungen an. Ebene 1 ist die Standard Warnstufe in der Befehlszeile.
- **Level2** -Level 2 zeigt alle Warnungen der Stufe 1 an, die weniger schwerwiegend sind als Ebene 1.
- **Level3** -Level 3 zeigt alle Warnungen der Stufe 2 sowie alle anderen für Produktionszwecke empfohlenen Warnungen an.
- In **Level4** -Level 4 werden alle Warnungen der Stufe 3 sowie Informations Warnungen angezeigt, die in den meisten Fällen problemlos ignoriert werden können.
- **Alle Warnungen aktivieren**: Aktiviert alle Warnungen, einschließlich standardmäßig deaktivierter Warnungen.

### <a name="treat-warnings-as-errors"></a>Warnungen als Fehler behandeln

Behandelt alle Compilerwarnungen als Fehler. Bei einem neuen Projekt ist es möglicherweise am besten, [/WX](wx-treat-linker-warnings-as-errors.md) in allen Kompilierungen zu verwenden. durch das Auflösen aller Warnungen wird sichergestellt, dass möglichst wenige schwer zu suchende Code Fehler gefunden werden.

### <a name="warning-version"></a>Warnungs Version

Blenden Sie Warnungen aus, die nach einer bestimmten Version des Compilers eingeführt wurden. Legt [/WV: xx\[. yy\[. zzzzz\]\]](wx-treat-linker-warnings-as-errors.md)fest.

### <a name="diagnostics-format"></a>Diagnose Format

Ermöglicht die umfassende Diagnose mit Spalten Informationen und Quell Kontext in Diagnosemeldungen.

**Optionen**

- Caretzeichen: stellt Spalten Informationen in der Diagnose Meldung bereit, und gibt die relevante Zeile des Quellcodes mit einem Caretzeichen an, das die problematische Spalte angibt.
- **Spalten Info** : gibt ggf. die Spaltennummer in der Zeile an, in der die Diagnose ausgegeben wird.
- **Klassisch** : behält die vorherigen, präzisen Diagnosemeldungen mit der Zeilennummer bei.

### <a name="sdl-checks"></a>SDL-Prüfungen

Weitere empfohlene Überprüfungen für Security Development Lifecycle (SDL) umfasst das Aktivieren zusätzlicher Funktionen zur sicheren Codegenerierung und ermöglicht zusätzliche sicherheitsrelevante Warnungen als Fehler. Legt [/SDL,/SDL-](sdl-enable-additional-security-checks.md)fest.

### <a name="multi-processor-compilation"></a>Kompilierung mit mehreren Prozessoren

Kompilierung mit mehreren Prozessoren

## <a name="cc-optimization-properties"></a>C/C++ Optimierungs Eigenschaften

### <a name="optimization"></a>Optimierung

Wählen Sie die Option für die Codeoptimierung aus. Wählen Sie Benutzer definiert, um bestimmte Optimierungs Optionen zu verwenden. Legt [/od](od-disable-debug.md), [/O1,/O2](o-options-optimize-code.md)fest.

**Optionen**

- **Benutzerdefiniert**: Benutzerdefinierte Optimierung
- **Deaktiviert**: Deaktivieren der Optimierung.
- **Maximale Optimierung (Größe bevorzugen)** , äquivalent zu/og/OS/Oy/Ob2/GS/GF/Gy
- **Maximale Optimierung (Geschwindigkeit bevorzugen)** : äquivalent zu/og/Oi/OT/Oy/Ob2/GS/GF/Gy
- **Optimierungen (Geschwindigkeit bevorzugen)** : äquivalent zu/og/Oi/OT/Oy/Ob2

### <a name="inline-function-expansion"></a>Inline Funktionserweiterung

Wählen Sie die Ebene der [Inline Funktions](../../cpp/inline-functions-cpp.md) Erweiterung für den Build aus. Legt [/ob1,/Ob2](ob-inline-function-expansion.md)fest.

**Optionen**

- **Default**
- **Deaktiviert** : deaktiviert die Inline Erweiterung, die standardmäßig aktiviert ist.
- **Nur __inline** : erweitert nur Funktionen, die als Inline-, __inline-, __forceinline-oder __inline C++ -oder in einer Member-Funktion gekennzeichnet sind, die innerhalb einer Klassen Deklaration definiert sind.
- **Alle geeigneten** : erweitert Funktionen, die als "Inline" oder "__inline" gekennzeichnet sind, und jede andere Funktion, die der Compiler auswählt (Erweiterung erfolgt nach dem Ermessen des Compilers, häufig auch als "Automatisches inlining" bezeichnet).

### <a name="enable-intrinsic-functions"></a>Intrinsische Funktionen aktivieren

Aktiviert intrinsische Funktionen.  Die Verwendung von intrinsischen Funktionen erzeugt schnelleren, aber möglicherweise größeren Code. Legt [/Oi](oi-generate-intrinsic-functions.md)fest.

### <a name="favor-size-or-speed"></a>Größe oder Geschwindigkeit bevorzugen

Gibt an, ob Codegröße oder Code Geschwindigkeit bevorzugt werden soll. "Globale Optimierung" muss aktiviert sein. Legt [/OT,/OS](os-ot-favor-small-code-favor-fast-code.md)fest.

**Optionen**

- Bevorzugen Sie kleinen Code zugunsten von **geringem Code** . Minimiert die Größe von exe-und DLLs, indem der Compiler angewiesen wird, die Größe gegenüber der Geschwindigkeit zu bevorzugen.
- Schnellen Code bevorzugen, schnellen Code bevorzugen. Maximiert die Geschwindigkeit von EXEs und DLLs, indem der Compiler angewiesen wird, die Geschwindigkeit der Größe zu bevorzugen. (Dies ist die Standardeinstellung.)
- **Weder** eine Größen-noch eine Geschwindigkeits Optimierung.

### <a name="omit-frame-pointers"></a>Frame Zeiger weglassen

Unterdrückt die Erstellung von Framezeigern im Anrufstapel.

### <a name="enable-fiber-safe-optimizations"></a>Fiber-sichere Optimierungen aktivieren

Aktiviert die Speicherplatz Optimierung bei Verwendung von Fibers und Thread lokalem Speicherzugriff. Legt [/gt](gt-support-fiber-safe-thread-local-storage.md)fest.

### <a name="whole-program-optimization"></a>Optimierung des gesamten Programms

Ermöglicht Modul übergreifende Optimierungen durch verzögern der Codegenerierung bis zur Verknüpfungs Zeit. erfordert, dass die Linkeroption "Link-Zeit Code Generierung" aktiviert ist. Legt [/GL](gl-whole-program-optimization.md)fest.

## <a name="cc-preprocessor-properties"></a>C/C++ präprozessoreigenschaften

### <a name="preprocessor-definitions"></a>Präprozessordefinitionen

Definiert Präprozessorsymbole für Ihre Quelldatei.

### <a name="undefine-preprocessor-definitions"></a>Präprozessordefinitionen aufheben

Gibt mindestens eine aufgehobene Präprozessordefinition an. Legt [/U](u-u-undefine-symbols.md)fest.

### <a name="undefine-all-preprocessor-definitions"></a>Alle Präprozessordefinitionen aufheben

Hebt die Definition aller zuvor definierten Präprozessorwerte auf. Legt [/u](u-u-undefine-symbols.md)fest.

### <a name="ignore-standard-include-paths"></a>Standardincludepfade ignorieren

Verhindert, dass der Compiler in Verzeichnissen, die in den INCLUDE-Umgebungsvariablen angegeben sind, nach Includedateien sucht.

### <a name="preprocess-to-a-file"></a>In einer Datei Vorverarbeiten

Führt eine Vorverarbeitung C++ von C-und Quelldateien durch und schreibt die vorverarbeitete Ausgabe in eine Datei. Diese Option unterdrückt die Kompilierung, sodass keine OBJ-Datei erzeugt wird.

### <a name="preprocess-suppress-line-numbers"></a>Vorverarbeitung unterdrücken von Zeilennummern

Preprocess ohne #line Direktiven.

### <a name="keep-comments"></a>Kommentare beibehalten

Unterdrückt die kommentarleiste aus dem Quellcode. erfordert, dass eine der Vorverarbeitungs Optionen festgelegt wird. Legt [/C](c-preserve-comments-during-preprocessing.md)fest.

## <a name="cc-code-generation-properties"></a>Eigenschaften derC++ C/Code-Generierung

### <a name="enable-string-pooling"></a>Zeichen folgen Pooling aktivieren

Ermöglicht es dem Compiler, während der Ausführung eine einzelne schreibgeschützte Kopie identischer Zeichen folgen im Programm Image und im Arbeitsspeicher zu erstellen. Dies führt zu kleineren Programmen, einer Optimierung namens Zeichen folgen Pooling. [/O1,/O2](o-options-optimize-code.md)und [/Zi](z7-zi-zi-debug-information-format.md) legen die Option [/GF](gf-eliminate-duplicate-strings.md) automatisch fest.

### <a name="enable-minimal-rebuild"></a>Minimale Neuerstellung aktivieren

Aktiviert die minimale Neuerstellung, die bestimmt, ob C++-Quelldateien, die geänderte C++-Klassendefinitionen enthalten (gespeichert in Headerdateien (.h)) neu kompiliert werden müssen.

### <a name="enable-c-exceptions"></a>C++-Ausnahmen aktivieren

Gibt das Ausnahmebehandlungsmodell an, das vom Compiler verwendet wird.

**Optionen**

- **Ja bei SEH-Ausnahmen** : das Ausnahme Behandlungsmodell, das asynchrone (strukturierte) und synchroneC++() Ausnahmen abfängt. Legt [/EHa](eh-exception-handling-model.md)fest.
- **Ja** , das Ausnahme Behandlungsmodell, das nur C++ Ausnahmen abfängt und den Compiler anweist, dass externe C-Funktionen nie C++ eine-Ausnahme auslösen. Legt [/EHsc](eh-exception-handling-model.md)fest.
- **Ja bei extern c-Funktionen** : das Ausnahme Behandlungsmodell, das C++ nur Ausnahmen abfängt und den Compiler anweist, zu übernehmen, dass externe c-Funktionen eine Ausnahme auslösen. Legt [/EHS](eh-exception-handling-model.md)fest.
- **No** -keine Ausnahmebehandlung.

### <a name="smaller-type-check"></a>Kleinere Typüberprüfung

Aktivieren Sie die Überprüfung der Konvertierung in kleinere Typen, nicht kompatibel mit einem anderen Optimierungstyp als "Debug". Legt [/RTCc](rtc-run-time-error-checks.md)fest.

### <a name="basic-runtime-checks"></a>Grundlegende Lauf Zeit Prüfungen

Führt grundlegende Lauf Zeit Fehlerüberprüfungen durch, die nicht mit allen anderen Typen als Debuggen kompatibel sind Legt [/RTCs,/RTCu,/RTC1](rtc-run-time-error-checks.md)fest.

**Optionen**

- **Stapel Rahmen** : aktiviert die Lauf Zeit Fehlerüberprüfung für Stapel Rahmen.
- **Nicht initialisierte Variablen** : meldet, wenn eine Variable verwendet wird, ohne initialisiert worden zu sein.
- **Both (/RTC1, equiv. to/RTCsu)** -Äquivalent von/RTCsu.
- **Standard** -standardmäßige Laufzeitüberprüfungen.

### <a name="runtime-library"></a>Laufzeitbibliothek

Dient zum Angeben der zu verknüpfenden Laufzeitbibliothek. Legt [/MT,/MTD,/MD,/MDD](md-mt-ld-use-run-time-library.md)fest.

**Optionen**

- **Multithread** : bewirkt, dass die Anwendung die statische Multithread-Version der Lauf Zeit Bibliothek verwendet.
- **Multithread-Debuggen** : Definiert _DEBUG und _MT. Diese Option führt auch dazu, dass der Compiler den Bibliotheksnamen "LIBCMTD.lib" in der .obj-Datei positioniert, sodass der Linker "LIBCMTD.lib" für das Auflösen externer Symbole verwendet.
- **Multithread-DLL** : bewirkt, dass Ihre Anwendung die Multithread-und dll-spezifische Version der Lauf Zeit Bibliothek verwendet. Definiert „_MT“ und „_DLL“ und bewirkt, dass der Compiler den Bibliotheksnamen "MSVCRT.lib" in der OBJ-Datei platziert.
- **Multithreaded-Debug-DLL** : Definiert _DEBUG, _MT und _DLL und bewirkt, dass Ihre Anwendung die Multithread-und dll-spezifische Version der Lauf Zeit Bibliothek verwendet. Außerdem wird verursacht, dass der Compiler den Bibliotheksnamen "MSVCRTD.lib" in der .obj-Datei positioniert.

### <a name="struct-member-alignment"></a>Ausrichtung von Strukturmembern

Gibt 1-, 2-, 4-oder 8-Byte-Begrenzungen für die Ausrichtung der Strukturmember an. Legt [/ZP](zp-struct-member-alignment.md)fest.

**Optionen**

- **1 Byte** packt Strukturen an 1-Byte-Begrenzungen. Identisch mit/ZP.
- **2** Byte packt Strukturen an 2-Byte-Begrenzungen.
- **4 Byte** -Pack-Strukturen auf 4-Byte-Begrenzungen.
- **8 Byte** -Pack-Strukturen an 8-Byte-Begrenzungen (Standard).
- **16 Byte** -Pack-Strukturen an 16-Byte-Begrenzungen.
- **Standard** -Standard-Ausrichtungs Einstellungen.

### <a name="security-check"></a>Sicherheitsüberprüfung

Die Sicherheitsprüfung hilft bei der Erkennung von Überläufen des Stapelpuffers. Hierbei handelt es sich um gängige Versuche, die Sicherheit eines Programms zu gefährden. 

**Optionen**

- **Sicherheitsüberprüfung deaktivieren**: Sicherheitsüberprüfung deaktivieren. Legt [/GS-](gs-buffer-security-check.md)fest.
- **Sicherheitsüberprüfung aktivieren**: Sicherheitsüberprüfung aktivieren. Legt [/GS](gs-buffer-security-check.md)fest.

### <a name="control-flow-guard"></a>Ablauf Steuerungs Schutz

Guard-Sicherheitsüberprüfung hilft bei der Erkennung von versuchen, eine Verteilung an einen ungültigen Codeblock durch 

**Optionen**

- **Ja** : Sicherheitsüberprüfung mit Schutz Sätzen aktivieren [/Guard: CF](guard-enable-control-flow-guard.md).
- **No**

### <a name="enable-function-level-linking"></a>Funktionslevel-Linking aktivieren

Ermöglicht dem Compiler, einzelne Funktionen in Form von kompilierten Funktionen (COMDATs) zu kompilieren. Zur Bearbeitung erforderlich, funktionieren weiterhin. Legt [/Gy](gy-enable-function-level-linking.md)fest.

### <a name="enable-parallel-code-generation"></a>Parallele Code Generierung aktivieren

Ermöglicht dem Compiler, parallelen Code für Schleifen zu generieren, die mithilfe #Pragma Schleife\[(hint_parallel (n)]) identifiziert werden, wenn die Optimierung aktiviert ist.

### <a name="enable-enhanced-instruction-set"></a>Erweiterten Anweisungs Satz aktivieren

Ermöglicht die Verwendung von Anweisungen, die auf Prozessoren gefunden werden, die erweiterte Anweisungs Sätze unterstützen, z. b. die SSE-, SSE2-, AVX-und AVX2-Erweiterungen für IA-32; AVX und AVX2 bis x64. Derzeit sind **/arch: SSE** und **/arch: SSE2** nur bei der Erstellung für die x86-Architektur verfügbar. Wenn keine Option angegeben ist, verwendet der Compiler Anweisungen, die auf Prozessoren gefunden werden, die SSE2 unterstützen. Die Verwendung erweiterter Anweisungen kann mit/arch: ia32 deaktiviert werden. Weitere Informationen finden Sie unter [/arch (x86)](arch-x86.md), [/arch (x64)](arch-x64.md) und [/arch (Arm)](arch-arm.md) .

**Optionen**

- **Streaming SIMD Extensions** Streaming SIMD Extensions. Legt **/arch: SSE** fest.
- **Streaming SIMD Extensions 2** -Streaming SIMD Extensions 2. Legt **/arch: SSE2**
- **Erweiterte Vektor Erweiterungen** -Erweiterte Vektor Erweiterungen. Legt **/arch: AVX** fest.
- **Erweiterte Vektor Erweiterungen 2** -Erweiterte Vektor Erweiterungen 2. Legt **/arch: AVX2**
- **Keine erweiterten Anweisungen** -keine erweiterten Anweisungen. Legt **/arch: ia32**
- **Nicht festgelegt** -nicht festgelegt.

### <a name="floating-point-model"></a>Gleit Komma Modell

Legt das Gleitkommamodell fest. Legt [/fp: präzise,/fp: Strict,/fp: fast](fp-specify-floating-point-behavior.md)fest.

**Optionen**

- **Genau** : Standardwert. Verbessert die Konsistenz von Gleit Komma Tests auf Gleichheit und Ungleichheit.
- **Strict** -das strengste Gleit Komma Modell. /fp: strict bewirkt, dass fp_contract off und fenv_access auf on gesetzt ist. /fp: nur impliziert und kann durch explizites angeben von/FP deaktiviert werden: außer-. Bei Verwendung mit/fp: außer-, erzwingt/fp: Strict eine strikte Gleit Komma Semantik, aber ohne Berücksichtigung von Ausnahme Ereignissen.
- **Schneller** : erstellt den schnellsten Code in den meisten Fällen.

### <a name="enable-floating-point-exceptions"></a>Gleit Komma Ausnahmen aktivieren

Verlässliches Modell für Gleitkommaausnahmen. Ausnahmen werden sofort ausgelöst, wenn sie auftreten.  Legt [/fp: außer](fp-specify-floating-point-behavior.md)fest.

### <a name="create-hotpatchable-image"></a>Hotpatchfähiges Image erstellen

Wenn Hotpatching vor auf ON fest steht, stellt der Compiler sicher, dass die erste Anweisung jeder Funktion zwei Bytes beträgt, was für das Hotpatching vor erforderlich ist.  Legt [/hotpatch](hotpatch-create-hotpatchable-image.md)fest.

### <a name="spectre-mitigation"></a>Spectre-Entschärfung

Spectre-entschärfungen für CVE 2017-5753. Legt [/Qspectre](qspectre.md)fest.

**Optionen**

- **Aktiviert** : enable Spectre Entschärfungs Feature für CVE 2017-5753
- **Deaktiviert** -nicht festgelegt.

## <a name="cc-language-properties"></a>C/C++ Language-Eigenschaften

### <a name="disable-language-extensions"></a>Spracherweiterungen deaktivieren

Unterdrückt oder aktiviert Spracherweiterungen. Legt [/Za](za-ze-disable-language-extensions.md)fest.

### <a name="conformance-mode"></a>Konformitäts Modus

Aktiviert oder unterdrückt den Konformitäts Modus. Legt [/permissive-](permissive-standards-conformance.md)fest.

### <a name="treat-wchar_t-as-built-in-type"></a>Wchar_t als integrierten Typ behandeln

Wenn diese Option angegeben ist, wird der Typ wchar_t zu einem systemeigenen Typ, der __wchar_t auf die gleiche Weise zugeordnet wird, wie Sie __int16 zugeordnet wird. [/Zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) ist standardmäßig aktiviert.

### <a name="force-conformance-in-for-loop-scope"></a>Konformität in for-Schleifen Bereich erzwingen

Wird verwendet, um C++ Standardverhalten für die for-Anweisungs Schleifen mit Microsoft-Erweiterungen zu implementieren. Legt [/Za,/Ze (Spracherweiterungen deaktivieren](za-ze-disable-language-extensions.md)) fest. Standardmäßig ist[/Zc:forScope](zc-forscope-force-conformance-in-for-loop-scope.md) aktiviert.

### <a name="remove-unreferenced-code-and-data"></a>Entfernen von nicht referenzierten Code und Daten

Wenn angegeben, generiert der Compiler keine Symbol Informationen für nicht referenzierten Code und Daten mehr.

### <a name="enforce-type-conversion-rules"></a>Typkonvertierungsregeln erzwingen

Wird verwendet, um einen Rvalue-Verweistyp als Ergebnis eines Umwandlungs Vorgangs in Übereinstimmung mit dem c++ 11-Standard zu identifizieren.

### <a name="enable-run-time-type-information"></a>Laufzeit-Typeninformation aktivieren

Fügt Code für die Überprüfung der C++-Objekttypen während der Laufzeit hinzu (Laufzeit-Typinformationen). Legt [/GR,/GR-](gr-enable-run-time-type-information.md)fest.

### <a name="open-mp-support"></a>Open MP-Unterstützung

Aktivieren von OpenMP 2,0-Spracherweiterungen. Legt [/OpenMP](openmp-enable-openmp-2-0-support.md)fest.

### <a name="c-language-standard"></a>C++-Sprachstandard

Bestimmt den C++ Sprachstandard, den der Compiler erzwingt. Es wird empfohlen, nach Möglichkeit die neueste Version zu verwenden. Legt [/Std: c++ 14,/Std: c++ 17,/Std: c + + Latest](std-specify-language-standard-version.md)fest.

**Optionen**

- **Default**
- **ISO c++ 14 Standard**
- **ISO c++ 17 Standard**
- **Vorschau: Features aus dem aktuellen C++ funktionierenden Entwurf**

### <a name="enable-c-modules-experimental"></a>Module C++ aktivieren (experimentell)

Experimentelle Unterstützung C++ für die Module TS und die Standard Bibliotheks Module.

## <a name="cc-precompiled-headers-properties"></a>Eigenschaften vonC++ C/vorkompilierten Headern

### <a name="precompiled-header"></a>Vorkompilierter Header

Vorkompilierten Header erstellen/verwenden: Ermöglicht die Erstellung oder Verwendung eines vorkompilierten Headers während der Erstellung. Legt [/Yc](yc-create-precompiled-header-file.md), [/Yu](yu-use-precompiled-header-file.md)fest.

**Optionen**

- **Create** -weist den Compiler an, eine vorkompilierte Header Datei (. pch) zu erstellen, die den Zustand der Kompilierung zu einem bestimmten Zeitpunkt darstellt.
- **Use** : weist den Compiler an, eine vorhandene vorkompilierte Header Datei (. pch) in der aktuellen Kompilierung zu verwenden.
- **Vorkompilierte Header** werden nicht verwendet. es werden keine vorkompilierten Header verwendet.

### <a name="precompiled-header-file"></a>Vorkompilierte Headerdatei

Gibt den Header Dateinamen an, der beim Erstellen oder Verwenden einer vorkompilierten Header Datei verwendet werden soll. Legt [/Yc](yc-create-precompiled-header-file.md), [/Yu]] (Yu-use-prekompiliert-Header-File.MD) fest.

### <a name="precompiled-header-output-file"></a>Vorkompilierte Header Ausgabedatei

Gibt den Pfad und/oder den Namen der generierten vorkompilierten Header Datei an. Legt [/FP](fp-name-dot-pch-file.md)fest.

## <a name="cc-output-files-properties"></a>Eigenschaften vonC++ C/Output-Dateien

### <a name="expand-attributed-source"></a>Attributierte Quelle erweitern

Erstellen Sie eine Listen Datei mit erweiterten Attributen in die Quelldatei. Legt [/FX](fx-merge-injected-code.md)fest.

### <a name="assembler-output"></a>Assembler-Ausgabe

Gibt die Inhalte der Ausgabedatei für die Assemblysprache an. Legt [/FA,/FAC,/FAS,/FACS](fa-fa-listing-file.md)fest.

**Optionen**

- **Keine Auflistung** -keine Auflistung.
- Assemblyausschließliches **auflisten** : Assemblycode;. asm
- **Assembly mit Computercode** , Computer-und Assemblycode;. COD
- **Assembly mit Quellcode** -Quell Code und Assemblycode;. asm
- **Assembly, Computercode und Quellassembly** , Computercode und Quellcode;. COD

### <a name="use-unicode-for-assembler-listing"></a>Unicode für assemblyauflistung verwenden

Bewirkt, dass die Ausgabedatei im UTF-8-Format erstellt wird.

### <a name="asm-list-location"></a>ASM-Listen Speicherort

Gibt den relativen Pfad und/oder Namen für die ASM-Listen Datei an. kann ein Datei-oder Verzeichnisname sein. Legt [/FA](fa-fa-listing-file.md)fest.

### <a name="object-file-name"></a>Name der Objektdatei

Gibt einen Namen an, um den Standardnamen der Objektdatei zu überschreiben. Dies kann ein Datei- oder Verzeichnisname sein. Legt [/FO](fo-object-file-name.md)fest.

### <a name="program-database-file-name"></a>Programmdatenbank-Dateiname

Gibt einen Namen für eine vom Compiler generierte PDB-Datei an. gibt auch den Basis Namen für die erforderliche vom Compiler generierte IDB-Datei an. kann ein Datei-oder Verzeichnisname sein. Legt [/FD](fd-program-database-file-name.md)fest.

### <a name="generate-xml-documentation-files"></a>XML-Dokumentationsdateien generieren

Gibt an, dass der Compiler XML-Dokumentations Kommentar Dateien generieren soll (. XDC). Legt [/doc](doc-process-documentation-comments-c-cpp.md)fest.

### <a name="xml-documentation-file-name"></a>Name der XML-Dokumentations Datei

Gibt den Namen der generierten XML-Dokumentationsdateien an. kann ein Datei-oder Verzeichnisname sein. Legt [/doc:\<Name >](doc-process-documentation-comments-c-cpp.md)fest.

## <a name="cc-browse-information-properties"></a>Eigenschaften fürC++ C/Browseinformationen

### <a name="enable-browse-information"></a>Browseinformationen aktivieren

Browseinformationen aktivieren: Gibt die Ebene der Browseinformationen in der BSC-Datei an. Legt [/fr](fr-fr-create-dot-sbr-file.md)fest.

### <a name="browse-information-file"></a>Informationsdatei durchsuchen

Datei durchsuchen: Gibt den optionalen Namen für die Browser Informationsdatei an. Legt [/fr\<Name >](fr-fr-create-dot-sbr-file.md)fest.

## <a name="cc-advanced-properties"></a>C/C++ Advanced-Eigenschaften

### <a name="calling-convention"></a>Aufrufkonvention

Wählen Sie die Standard Aufruf Konvention für Ihre Anwendung aus (kann von einer Funktion überschrieben werden). Legt [/GD,/GR,/gz,/GV](gd-gr-gv-gz-calling-convention.md)fest.

**Optionen**

- **__cdecl** : gibt die __cdecl-Aufruf Konvention für alle Funktionen C++ außer Element Funktionen und Funktionen an, die als __stdcall oder __fastcall gekennzeichnet sind.
- **__fastcall** : gibt die __fastcall-Aufruf Konvention für alle Funktionen C++ außer Element Funktionen und Funktionen an, die als __cdecl oder __stdcall gekennzeichnet sind. Alle __fastcall-Funktionen müssen über Prototypen verfügen.
- **__stdcall** : gibt die __stdcall-Aufruf Konvention für alle Funktionen C++ außer Element Funktionen und Funktionen an, die als __cdecl oder __fastcall gekennzeichnet sind. Alle __stdcall-Funktionen müssen über Prototypen verfügen.
- **__vectorcall** : gibt die __vectorcall-Aufruf Konvention für alle Funktionen C++ außer Element Funktionen und Funktionen an, die als __cdecl, __fastcall oder __stdcall markiert sind. Alle __vectorcall-Funktionen müssen über Prototypen verfügen.

### <a name="compile-as"></a>Kompilieren als

Wählen Sie die Kompilierungssprachenoption für C- und CPP-Dateien aus. Legt [/TC,/TP](tc-tp-tc-tp-specify-source-file-type.md)fest.

**Optionen**

- **Standard**: die Standardeinstellung.
- **Als C-Code kompilieren**: als C-Code kompilieren.
- **Als C++-Code kompilieren**: als C++-Code kompilieren.

### <a name="disable-specific-warnings"></a>Bestimmte Warnungen deaktivieren

Deaktivieren Sie die gewünschten Warnungs Nummern. Stellen Sie Zahlen in eine durch Semikolons getrennte Liste. Legt [/WD\<NUM >](compiler-option-warning-level.md)fest.

### <a name="forced-include-file"></a>Erzwungene Includedatei

eine oder mehrere explizite Includedateien. Legt [/fi\<Name >](fi-name-forced-include-file.md)fest.

### <a name="forced-using-file"></a>Erzwungene #using Datei

Gibt eine oder mehrere erzwungene #using Dateien an. Legt [/FU\<Name >](fu-name-forced-hash-using-file.md)fest.

### <a name="show-includes"></a>Includedateien anzeigen

Generiert eine Liste der Includedateien mit Compilerausgabe. Legt [/showIncludes](showincludes-list-include-files.md)fest.

### <a name="use-full-paths"></a>Vollständige Pfade verwenden

Verwenden Sie vollständige Pfade in Diagnosemeldungen. Legt [/FC](fc-full-path-of-source-code-file-in-diagnostics.md)fest.

### <a name="omit-default-library-name"></a>Standard Bibliotheksnamen weglassen

Fügen Sie keine Standard Bibliotheksnamen in OBJ-Dateien ein. Legt [/Zl](zl-omit-default-library-name.md)fest.

### <a name="internal-compiler-error-reporting"></a>Interne compilerfehlerberichterstattung

Gibt an, wie interne Tool Fehler an Microsoft gemeldet werden sollen.  Der Standardwert in der IDE ist prompt.  Der Standardwert von Befehlszeilenbuilds ist Queue. Legt [/errorreport:\[Method]] (errorreport-Report-Internal-Compiler-Errors.MD) fest.

**Optionen**

- Keinen **Bericht senden** : Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.
- **Eingabeaufforderung sofort** : Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler erhalten.
- **Warteschlange für nächste Anmeldung** : Fügt den Fehlerbericht in die Warteschlange ein Wenn Sie sich mit Administratorrechten anmelden, wird ein Popup Fenster angezeigt, in dem Sie alle Fehler seit der letzten Anmeldung melden können (Sie werden nicht mehr als einmal alle drei Tage aufgefordert, Berichte zu Fehlern zu senden). Queue ist die Standardeinstellung, wenn eine Anwendung in der Befehlszeile kompiliert wird.
- **Automatisch senden** : sendet automatisch Berichte interner Compilerfehler an Microsoft. Um diese Option zu aktivieren, müssen Sie zunächst der Richtlinie für die Datensammlung von Microsoft% 27 s zustimmen. Wenn Sie/errorreport: Send zum ersten Mal auf einem Computer angeben, wird eine compilernachricht auf eine Website verwiesen, die die Richtlinie für die Datensammlung von Microsoft% 27 s enthält.

### <a name="treat-specific-warnings-as-errors"></a>Bestimmte Warnungen als Fehler behandeln

Behandelt die spezifische Compilerwarnung als Fehler, wobei n eine Compilerwarnung ist.

### <a name="additional-options"></a>Zusätzliche Optionen

Zusätzliche Optionen.
