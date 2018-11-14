---
title: Compileroptionen nach Kategorien sortiert
ms.date: 11/12/2018
helpviewer_keywords:
- compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
ms.openlocfilehash: aa93158e518950efa9d1f2f8092aeabbc3c7724c
ms.sourcegitcommit: 99437d7da4528ce72cabe6b6a65a9be5dfd090f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "51598820"
---
# <a name="compiler-options-listed-by-category"></a>Compileroptionen nach Kategorien sortiert

Dieser Artikel enthält eine nach Kategorien sortierte Liste der Compileroptionen. Eine alphabetische Liste finden Sie unter [Compiler Options Listed Alphabetically](compiler-options-listed-alphabetically.md).

### <a name="optimization"></a>Optimierung

|Option|Zweck|
|------------|-------------|
|[/O1](o1-o2-minimize-size-maximize-speed.md)|Erstellt kompakten Code.|
|[/O2](o1-o2-minimize-size-maximize-speed.md)|Erstellt schnellen Code.|
|[/Ob](ob-inline-function-expansion.md)|Steuert Inline-Erweiterung.|
|[/Od](od-disable-debug.md)|Deaktiviert Optimierung.|
|[/Og](og-global-optimizations.md)|Veraltet. Verwendet globale Optimierung.|
|[/Oi](oi-generate-intrinsic-functions.md)|Erstellt systeminterne Funktionen.|
|[/Os](os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt kompakten Code.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt schnellen Code.|
|[/Ox](ox-full-optimization.md)|Verwendet maximale Optimierung (/Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Unterdrückt Framezeiger. (nur x86)|
|[/favor](favor-optimize-for-architecture-specifics.md)|Erzeugt Code, der für eine bestimmte Architektur optimiert wird, oder für einen Bereich von Architekturen.|

### <a name="code-generation"></a>Codeerzeugung

|Option|Zweck|
|------------|-------------|
|[/arch](arch-x86.md)|Verwendet SSE- oder SSE2-Anweisungen bei der Codeerzeugung. (nur x86)|
|[/clr](clr-common-language-runtime-compilation.md)|Erzeugt eine Ausgabedatei, die auf der Common Language Runtime ausgeführt werden kann.|
|[/EH](eh-exception-handling-model.md)|Gibt das Modell der Ausnahmebehandlung an.|
|[/fp](fp-specify-floating-point-behavior.md)|Gibt das Gleitkommaverhalten an.|
|[/GA](ga-optimize-for-windows-application.md)|Optimiert Windows-Anwendungen.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__cdecl` -Aufrufkonvention. (nur x86)|
|[/Ge](ge-enable-stack-probes.md)|Veraltet. Aktiviert Stapelüberprüfungen.|
|[/GF](gf-eliminate-duplicate-strings.md)|Aktiviert Stringpooling.|
|[/Gh](gh-enable-penter-hook-function.md)|Ruft die Hookfunktion `_penter`auf.|
|[/GH](gh-enable-pexit-hook-function.md)|Ruft die Hookfunktion `_pexit`auf.|
|[/GL](gl-whole-program-optimization.md)|Aktiviert die Optimierung des gesamten Programms.|
|[/Gm](gm-enable-minimal-rebuild.md)|Veraltet. Aktiviert minimale Neuerstellung.|
|[/GR](gr-enable-run-time-type-information.md)|Aktiviert Laufzeit-Typeninformation (RTTI).|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__fastcall` -Aufrufkonvention. (nur x86)|
|[/GS](gs-buffer-security-check.md)|Überprüft die Puffersicherheit.|
|[/Gs](gs-control-stack-checking-calls.md)|Steuert Stapelüberprüfungen|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Unterstützt Fiber-Sicherheit für Daten, die mit statischem lokalen Threadspeicher zugewiesen werden.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Fügt Sicherheitsüberprüfungen zum Ablaufsteuerungsschutz hinzu.|
|[/Gv](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__vectorcall` -Aufrufkonvention. (nur x86 und x64)|
|[/Gw](gw-optimize-global-data.md)|Ermöglicht programmübergreifende globale Datenoptimierung.|
|[/GX](gx-enable-exception-handling.md)|Veraltet. Aktiviert synchrone Ausnahmebehandlung. Verwenden Sie stattdessen [/EH](eh-exception-handling-model.md) .|
|[/Gy](gy-enable-function-level-linking.md)|Aktiviert Funktionslevel-Linking.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Veraltet. Ermöglicht schnelle Überprüfungen. (Entspricht [/RTC1](rtc-run-time-error-checks.md).)|
|[/Gz](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__stdcall` -Aufrufkonvention. (nur x86)|
|[/homeparams](homeparams-copy-register-parameters-to-stack.md)|Erzwingt, dass in Registern übergebene Parameter beim Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden. Diese Compileroption steht nur für die X64-Compiler (systemeigene und cross-Compiler).|
|[/hotpatch](hotpatch-create-hotpatchable-image.md)|Erstellt ein Hotpatch-fähiges Abbild.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Generiert schnelle Transzendente.|
|[QIfist](qifist-suppress-ftol.md)|Veraltet. Unterdrückt den Aufruf der `_ftol` -Hilfsfunktion, wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich ist. (nur x86)|
|[/Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Entfernt `fwait` -Befehle in `try` -Blöcken.|
|[/Qpar](qpar-auto-parallelizer.md)|Ermöglicht automatische Parallelisierung von Schleifen.|
|[/Qpar-report](qpar-report-auto-parallelizer-reporting-level.md)|Aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Verwendet ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.|
|[/Qspectre](qspectre.md)|Entschärfungen für CVE 2017-5753 für eine Klasse von Spectre-Angriffen zu aktivieren.|
|[/Qvec-report](qvec-report-auto-vectorizer-reporting-level.md)|Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.|
|[/RTC](rtc-run-time-error-checks.md)|Aktiviert Laufzeitfehlerüberprüfung.|
|[/volatile](volatile-volatile-keyword-interpretation.md)|Wählt aus, wie das volatile-Schlüsselwort interpretiert wird.|

### <a name="output-files"></a>Ausgabedateien

|Option|Zweck|
|------------|-------------|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|
|[/FA](fa-fa-listing-file.md)|Konfiguriert eine Assemblylistendatei.|
|[/Fa](fa-fa-listing-file.md)|Erstellt eine Assemblylistendatei.|
|[/Fd](fd-program-database-file-name.md)|Benennt die Programmdatenbankdatei um.|
|[/Fe](fe-name-exe-file.md)|Benennt die ausführbare Datei um.|
|[/Fi](fi-preprocess-output-file-name.md)|Gibt den Namen der vorverarbeiteten Ausgabedatei an.|
|[/Fm](fm-name-mapfile.md)|Erstellt eine Zuordnungsdatei.|
|[/Fo](fo-object-file-name.md)|Erstellt eine Objektdatei.|
|[/Fp](fp-name-dot-pch-file.md)|Gibt den Namen einer vorkompilierten Headerdatei an.|
|[/FR, /Fr](fr-fr-create-dot-sbr-file.md)|Name generiert Browser SBR-Dateien.|

### <a name="preprocessor"></a>Präprozessor

|Option|Zweck|
|------------|-------------|
|[/AI](ai-specify-metadata-directories.md)|Gibt das zu durchsuchende Verzeichnis an, um Dateiverweise aufzulösen, die an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben wurden.|
|[/C](c-preserve-comments-during-preprocessing.md)|Behält Kommentare beim Präprozessorlauf bei|
|[/D](d-preprocessor-definitions.md)|Definiert Konstanten und Makros.|
|[/E](e-preprocess-to-stdout.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|
|[/FI](fi-name-forced-include-file.md)|Führt eine Vorverarbeitung der angegebenen Includedatei durch.|
|[/FU](fu-name-forced-hash-using-file.md)|Erzwingt die Verwendung eines Dateinamens, als ob er an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben worden wäre.|
|[/Fx](fx-merge-injected-code.md)|Führt eingefügten Code mit der Quelldatei zusammen.|
|[/I](i-additional-include-directories.md)|Sucht in einem Verzeichnis nach Includedateien.|
|[/P](p-preprocess-to-a-file.md)|Schreibt Präprozessorausgaben in eine Datei.|
|[/U](u-u-undefine-symbols.md)|Entfernt ein vorkompiliertes Makro.|
|[/u](u-u-undefine-symbols.md)|Entfernt alle vorkompilierten Makros.|
|[/X](x-ignore-standard-include-paths.md)|Ignoriert das standardmäßige Includeverzeichnis.|

### <a name="language"></a>Sprache

|Option|Zweck|
|------------|-------------|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Constexpr-Auswertung zum Zeitpunkt der Kompilierung steuern.|
|[/openmp](openmp-enable-openmp-2-0-support.md)|Ermöglicht [#pragma omp](../../preprocessor/omp.md) im Quellcode.|
|[/vd](vd-disable-construction-displacements.md)|Unterdrückt oder aktiviert ausgeblendete `vtordisp` -Klassenmember.|
|[/vmb](vmb-vmg-representation-method.md)|Verwendet bestmögliche Basis für Zeiger auf Member.|
|[/vmg](vmb-vmg-representation-method.md)|Verwendet volle Allgemeingültigkeit für Zeiger auf Member.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Deklariert mehrfache Vererbung.|
|[/vms](vmm-vms-vmv-general-purpose-representation.md)|Deklariert einfache Vererbung.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Deklariert virtuelle Vererbung.|
|[/Z7](z7-zi-zi-debug-information-format.md)|Generiert C# 7.0-kompatible Debuginformationen.|
|[/Za](za-ze-disable-language-extensions.md)|Deaktiviert Spracherweiterungen.|
|[/Zc](zc-conformance.md)|Legt Standardverhalten unter [/Ze](za-ze-disable-language-extensions.md)fest.|
|[/Ze](za-ze-disable-language-extensions.md)|Veraltet. Aktiviert Spracherweiterungen.|
|[/Zf](zf.md)|Verbessert die PDB-Datei Zeitpunkt der Generierung in parallele Builds.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Fügt Debuginformationen in eine Programmdatenbank ein, die mit Bearbeiten und Fortfahren kompatibel ist. (nur x86)|
|[/Zi](z7-zi-zi-debug-information-format.md)|Erzeugt vollständige Debuginformationen.|
|[/Zl](zl-omit-default-library-name.md)|Entfernt den Standardbibliotheksnamen aus der OBJ-Datei.|
|[/Zp](zp-struct-member-alignment.md) *n*|Komprimiert Strukturmember.|
|[/Zs](zs-syntax-check-only.md)|Prüft nur die Syntax.|
|[/ZW](zw-windows-runtime-compilation.md)|Erzeugt eine Ausgabedatei an, in der Windows-Runtime ausgeführt.|

### <a name="linking"></a>Verknüpfen

|Option|Zweck|
|------------|-------------|
|[/F](f-set-stack-size.md)|Legt die Stapelgröße fest.|
|[/LD](md-mt-ld-use-run-time-library.md)|Erstellt eine Dynamic Link Library (DLL).|
|[/LDd](md-mt-ld-use-run-time-library.md)|Erstellt eine Debug-Dynamic Link Library.|
|[/link](link-pass-options-to-linker.md)|Übergibt die angegebene Option an LINK.|
|[/LN](ln-create-msil-module.md)|Generiert ein MSIL-Modul.|
|[/MD](md-mt-ld-use-run-time-library.md)|Kompiliert, um mit MSVCRT.LIB eine Multithread-DLL zu erstellen.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Kompiliert, um mit MSVCRTD.LIB eine Multithread-DLL für den Debugger zu erstellen.|
|[/MT](md-mt-ld-use-run-time-library.md)|Kompiliert, um mit LIBCMT.LIB eine ausführbare Multithreaddatei zu erstellen.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Kompiliert, um mit LIBCMTD.LIB eine ausführbare Multithreaddatei für den Debugger zu erstellen.|

### <a name="miscellaneous"></a>Verschiedenes

|Option|Zweck|
|------------|-------------|
|[/?](help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|
|[@](at-specify-a-compiler-response-file.md)|Legt eine Antwortdatei fest.|
|[/analyze](analyze-code-analysis.md)|Aktiviert die Codeanalyse.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Erhöht die Anzahl von adressierbaren Abschnitten in einer OBJ-Datei.|
|[/c](c-compile-without-linking.md)|Kompiliert ohne Verknüpfen.|
|[/cgthreads](cgthreads-code-generation-threads.md)|Gibt die Anzahl der cl.exe-Threads an, die für Optimierung und Codegenerierung verwendet werden.|
|[/errorReport](errorreport-report-internal-compiler-errors.md)|Ermöglicht Ihnen, Informationen über interne Compilerfehler direkt an das Visual C++-Team zu senden.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Zeigt den vollständigen Pfad der Quellcodedateien im Diagnosetext in CL.EXE an.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Erzwingt die Serialisierung von Schreibvorgängen auf die Programmdatenbank (PDB) mithilfe von MSPDBSRV.EXE.|
|[/H](h-restrict-length-of-external-names.md)|Veraltet. Beschränkt die Länge externer (öffentlicher) Namen.|
|[/HELP](help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|
|[/J](j-default-char-type-is-unsigned.md)|Ändert den `char` -Standardtyp.|
|[/ JMC](jmc.md)|Unterstützt native C++ nur mein Code debuggen.|
|[/kernel](kernel-create-kernel-mode-binary.md)|Der Compiler und der Linker erstellen eine Binärdatei, die im Kernel von Windows ausgeführt werden kann.|
|[/MP](mp-build-with-multiple-processes.md)|Erstellt mehrere Quelldateien gleichzeitig.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Unterdrückt die Anzeige von Startinformationen.|
|[/sdl](sdl-enable-additional-security-checks.md)|Aktiviert zusätzliche Sicherheitsfunktionen und Warnungen.|
|[/showIncludes](showincludes-list-include-files.md)|Zeigt während der Kompilierung eine Liste aller Includedateien an.|
|[/Tc](tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C-Quelldatei an.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien c sind.|
|[/Tp](tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C++-Quelldatei an.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien C++ sind.|
|[/V](v-version-number.md)|Veraltet. Legt die Versionszeichenfolge fest.|
|[/w](compiler-option-warning-level.md)|Deaktiviert alle Warnungen.|
|[/W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Legt die ausgegebene Warnstufe fest.|
|[/w1, /w2, /w3, /w4](compiler-option-warning-level.md)|Legt die Warnstufe für die angegebene Warnung fest.|
|[/Wall](compiler-option-warning-level.md)|Aktiviert alle Warnungen, einschließlich standardmäßig deaktivierter Warnmeldungen.|
|[/wd](compiler-option-warning-level.md)|Deaktiviert die angegebene Warnung.|
|[/we](compiler-option-warning-level.md)|Behandelt die angegebene Warnung als einen Fehler.|
|[/WL](wl-enable-one-line-diagnostics.md)|Aktiviert einzeilige Diagnose für Fehler- und Warnmeldungen beim Kompilieren von C++-Quellcode aus der Befehlszeile.|
|[/wo](compiler-option-warning-level.md)|Zeigt die angegebene Warnung nur einmal an.|
|[/Wv](compiler-option-warning-level.md)|Deaktiviert die Warnungen, die durch spätere Versionen des Compilers eingeführt wurden.|
|[/WX](compiler-option-warning-level.md)|Behandelt Warnungen wie Fehler.|
|[/Yc](yc-create-precompiled-header-file.md)|Erstellen. PCH-Datei.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Veraltet. Legt vollständige Debuginformationen in allen Objektdateien ab. Verwenden Sie stattdessen [/Zi](z7-zi-zi-debug-information-format.md) .|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Fügt beim Erstellen einer Debugbibliothek einen PCH-Verweis ein.|
|[/Yu](yu-use-precompiled-header-file.md)|Verwendet eine vorkompilierte Headerdatei beim Erstellungsvorgang.|
|[/Y-](y-ignore-precompiled-header-options.md)|Ignoriert alle anderen Optionen für vorkompilierte Header im aktuellen Erstellungsprozess.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Legt die maximale Speicherbelegung für den vorkompilierten Header fest.|
|[/await](await-enable-coroutine-support.md)|Ermöglichen von Erweiterungen von Coroutinen (fortsetzbare Funktionen).|
|[/source-charset](source-charset-set-source-character-set.md)|Festlegen des quellzeichensatzes.|
|[/execution-charset](execution-charset-set-execution-character-set.md)|Festlegen des ausführungszeichensatzes.|
|[/utf-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Set Zeichensätze Quell- und auf UTF-8.|
|[/validate-charset](validate-charset-validate-for-compatible-characters.md)|UTF-8-Dateien auf nur kompatible Zeichen zu überprüfen.|
|[/ Diagnostics](diagnostics-compiler-diagnostic-options.md)|Steuert das Format von diagnosemeldungen.|
|[/permissive-](permissive-standards-conformance.md)|Legen Sie die Standard-Standards-Modus.|
|[/std](std-specify-language-standard-version.md)|C++-standard-Version Kompatibilität Selektor.|

### <a name="deprecated-and-removed-compiler-options"></a>Veraltete und entfernte Compileroptionen

|Option|Zweck|
|------------|-------------|
|[/clr:noAssembly](clr-common-language-runtime-compilation.md)|Veraltet. Verwenden Sie stattdessen [/LN (Create MSIL Module)](ln-create-msil-module.md) .|
|[/Fr](fr-fr-create-dot-sbr-file.md)|Veraltet. Erstellt eine Browseinformationsdatei ohne lokale Variablen.|
|[/Ge](ge-enable-stack-probes.md)|Veraltet. Aktiviert Stapelüberprüfungen. Standardmäßig aktiviert.|
|[/Gm](gm-enable-minimal-rebuild.md)|Veraltet. Aktiviert minimale Neuerstellung.|
|[/GX](gx-enable-exception-handling.md)|Veraltet. Aktiviert synchrone Ausnahmebehandlung. Verwenden Sie stattdessen [/EH](eh-exception-handling-model.md) .|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Veraltet. Ermöglicht schnelle Überprüfungen. Verwenden Sie stattdessen [/RTC1](rtc-run-time-error-checks.md) .|
|[/H](h-restrict-length-of-external-names.md)|Veraltet. Beschränkt die Länge externer (öffentlicher) Namen.|
|[/Og](og-global-optimizations.md)|Veraltet. Verwendet globale Optimierung.|
|[QIfist](qifist-suppress-ftol.md)|Veraltet. Wurde verwendet, um anzugeben, wie aus einem Gleitkommatyp in einen ganzzahligen Typ konvertiert werden soll.|
|[/V](v-version-number.md)|Veraltet. Legt die Versionszeichenfolge der OBJ-Datei fest.|
|[/Wp64](wp64-detect-64-bit-portability-issues.md)|Veraltet. Erkennt 64-Bit-Portabilitätsprobleme.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Veraltet. Legt vollständige Debuginformationen in allen Objektdateien ab. Verwenden Sie stattdessen [/Zi](z7-zi-zi-debug-information-format.md) .|
|[/Zc:forScope-](zc-forscope-force-conformance-in-for-loop-scope.md)|Veraltet. Deaktiviert Übereinstimmung in einem for-Schleifenbereich.|
|[/Ze](za-ze-disable-language-extensions.md)|Veraltet. Aktiviert Spracherweiterungen.|
|[/Zg](zg-generate-function-prototypes.md)|In Visual C++ 2015 entfernt. Erzeugt Funktionsprototypen.|

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)<br/>
[Compileroptionen](compiler-options.md)<br/>
[Festlegen von Compileroptionen](setting-compiler-options.md)<br/>
