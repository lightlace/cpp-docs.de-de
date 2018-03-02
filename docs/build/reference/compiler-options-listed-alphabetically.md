---
title: Compileroptionen in alphabetischer Reihenfolge | Microsoft Docs
ms.custom: 
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- compiler options, C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7906893c1dce20344a9da805ad508a7836b1291d
ms.sourcegitcommit: d24de38f9da844f824acb9d200a3f263077145fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="compiler-options-listed-alphabetically"></a>Compileroptionen alphabetisch sortiert

In diesem Abschnitt finden Sie eine vollständige Liste der Compileroptionen in alphabetischer Reihenfolge. Eine nach Kategorien sortierte Liste finden Sie unter der [Compileroptionen nach Kategorien sortiert](compiler-options-listed-by-category.md).

|Option|Zweck|
|------------|-------------|
|[@](at-specify-a-compiler-response-file.md)|Legt eine Antwortdatei fest.|
|[/?](help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|
|[/AI](ai-specify-metadata-directories.md)|Gibt das zu durchsuchende Verzeichnis an, um Dateiverweise aufzulösen, die an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben wurden.|
|[/analyze](analyze-code-analysis.md)|Aktiviert die Codeanalyse.|
|[/arch](arch-minimum-cpu-architecture.md)|Gibt die Architektur für die Codegenerierung an.|
|[/await](await-enable-coroutine-support.md)|Aktivieren Sie Erweiterungen für Coroutinen (fortsetzbare Funktionen).|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Erhöht die Anzahl von adressierbaren Abschnitten in einer OBJ-Datei.|
|[/C](c-preserve-comments-during-preprocessing.md)|Behält Kommentare beim Präprozessorlauf bei|
|[/c](c-compile-without-linking.md)|Kompiliert ohne Verknüpfen.|
|[/cgthreads](cgthreads-code-generation-threads.md)|Gibt die Anzahl der cl.exe-Threads an, die für Optimierung und Codegenerierung verwendet werden.|
|[/clr](clr-common-language-runtime-compilation.md)|Erzeugt eine Ausgabedatei, die auf der Common Language Runtime ausgeführt werden kann.|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Constexpr-Auswertung zum Zeitpunkt der Kompilierung zu steuern.|
|[/D](d-preprocessor-definitions.md)|Definiert Konstanten und Makros.|
|[/diagnostics](diagnostics-compiler-diagnostic-options.md)|Steuert das Format der diagnosemeldungen an.|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|
|[/E](e-preprocess-to-stdout.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|
|[/EH](eh-exception-handling-model.md)|Gibt das Modell der Ausnahmebehandlung an.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|
|[/errorReport](errorreport-report-internal-compiler-errors.md)|Ermöglicht Ihnen, Informationen über interne Compilerfehler direkt an das Visual C++-Team zu senden.|
|[/execution-charset](execution-charset-set-execution-character-set.md)|Der ausführungszeichensatz festlegen.|
|[/F](f-set-stack-size.md)|Legt die Stapelgröße fest.|
|[/favor](favor-optimize-for-architecture-specifics.md)|Erzeugt optimierten Code für eine bestimmte [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Architektur oder für spezifische Merkmale der Mikroarchitekturen von AMD64- und Extended Memory 64 Technology (EM64T)-Architekturen.|
|[/FA](fa-fa-listing-file.md)|Erstellt eine Listendatei.|
|[/Fa](fa-fa-listing-file.md)|Legt den Namen der Listendatei fest.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Anzeige des vollständigen Pfads der Quellcodedateien im Diagnosetext in "cl.exe".|
|[/Fd](fd-program-database-file-name.md)|Benennt die Programmdatenbankdatei um.|
|[/Fe](fe-name-exe-file.md)|Benennt die ausführbare Datei um.|
|[/FI](fi-name-forced-include-file.md)|Führt eine Vorverarbeitung der angegebenen Includedatei durch.|
|[/Fi](fi-preprocess-output-file-name.md)|Legt den vorverarbeiteten Ausgabedateinamen fest.|
|[/Fm](fm-name-mapfile.md)|Erstellt eine Zuordnungsdatei.|
|[/Fo](fo-object-file-name.md)|Erstellt eine Objektdatei.|
|[/fp](fp-specify-floating-point-behavior.md)|Gibt das Gleitkommaverhalten an.|
|[/Fp](fp-name-dot-pch-file.md)|Gibt den Namen einer vorkompilierten Headerdatei an.|
|[/FR](fr-fr-create-dot-sbr-file.md)<br /><br /> [/Fr](fr-fr-create-dot-sbr-file.md)|Erstellt Browserdateien. **/Fr** ist veraltet.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Erzwingt die Serialisierung von Schreibvorgängen auf die Programmdatenbank (PDB) mithilfe von MSPDBSRV.EXE.|
|[/FU](fu-name-forced-hash-using-file.md)|Erzwingt die Verwendung eines Dateinamens, als ob er an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben worden wäre.|
|[/Fx](fx-merge-injected-code.md)|Führt eingefügten Code mit der Quelldatei zusammen.|
|[/GA](ga-optimize-for-windows-application.md)|Codeoptimierung für Windows-Anwendung.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__cdecl` -Aufrufkonvention (nur x86).|
|[/Ge](ge-enable-stack-probes.md)|Veraltet. Aktiviert Stapelüberprüfungen.|
|[/GF](gf-eliminate-duplicate-strings.md)|Aktiviert Stringpooling.|
|[/GH](gh-enable-pexit-hook-function.md)|Ruft die Hookfunktion `_pexit`auf.|
|[/Gh](gh-enable-penter-hook-function.md)|Ruft die Hookfunktion `_penter`auf.|
|[/GL](gl-whole-program-optimization.md)|Aktiviert die Optimierung des gesamten Programms.|
|[/Gm](gm-enable-minimal-rebuild.md)|Aktiviert minimale Neuerstellung.|
|[/GR](gr-enable-run-time-type-information.md)|Aktiviert Laufzeit-Typeninformation (RTTI).|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__fastcall` -Aufrufkonvention (nur x86).|
|[/GS](gs-buffer-security-check.md)|Führt eine Puffer-Sicherheitsüberprüfung durch.|
|[/Gs](gs-control-stack-checking-calls.md)|Steuert Stapelüberprüfungen|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Unterstützt die Fiber-Sicherheit für Daten, die mit statischem lokalen Thread-Speicher zugewiesen werden.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Fügt Sicherheitsüberprüfungen zum Ablaufsteuerungsschutz hinzu.|
|[/Gv](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__vectorcall` -Aufrufkonvention. (nur x86 und x64)|
|[/Gw](gw-optimize-global-data.md)|Ermöglicht programmübergreifende globale Datenoptimierung.|
|[/GX](gx-enable-exception-handling.md)|Veraltet. Aktiviert synchrone Ausnahmebehandlung. Verwendung [/EH](eh-exception-handling-model.md) stattdessen.|
|[/ Gy](gy-enable-function-level-linking.md)|Aktiviert Funktionslevel-Linking.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Veraltet. Identisch mit [/RTC1](rtc-run-time-error-checks.md).|
|[/Gz](gd-gr-gv-gz-calling-convention.md)|Verwendet die `__stdcall` -Aufrufkonvention (nur x86).|
|[/H](h-restrict-length-of-external-names.md)|Veraltet. Beschränkt die Länge externer (öffentlicher) Namen.|
|[/HELP](help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|
|[/homeparams](homeparams-copy-register-parameters-to-stack.md)|Erzwingt, dass in Registern übergebene Parameter beim Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden. Diese Compileroption gilt nur für die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Compiler (systemeigene und Cross-Compiler).|
|[/hotpatch](hotpatch-create-hotpatchable-image.md)|Erstellt ein Hotpatch-fähiges Abbild.|
|[/I](i-additional-include-directories.md)|Sucht in einem Verzeichnis nach Includedateien.|
|[/J](j-default-char-type-is-unsigned.md)|Ändert den `char` -Standardtyp.|
|[/kernel](kernel-create-kernel-mode-binary.md)|Der Compiler und der Linker erstellen eine Binärdatei, die im Kernel von Windows ausgeführt werden kann.|
|[/LD](md-mt-ld-use-run-time-library.md)|Erstellt eine Dynamic Link Library (DLL).|
|[/LDd](md-mt-ld-use-run-time-library.md)|Erstellt eine Debug-Dynamic Link Library.|
|[/link](link-pass-options-to-linker.md)|Übergibt die angegebene Option an LINK.|
|[/LN](ln-create-msil-module.md)|Generiert ein MSIL-Modul.|
|[/MD](md-mt-ld-use-run-time-library.md)|Erstellt mit MSVCRT.lib eine Multithread-DLL.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Erstellt mit MSVCRTD.lib eine Multithread-DLL für den Debugger.|
|[/MP](mp-build-with-multiple-processes.md)|Kompiliert mehrere Quelldateien unter Verwendung mehrerer Prozesse.|
|[/MT](md-mt-ld-use-run-time-library.md)|Erstellt mit LIBCMT.lib eine ausführbare Multithread-Datei.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Erstellt mit LIBCMTD.lib eine ausführbare Multithread-Datei für den Debugger.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Unterdrückt die Anzeige von Startinformationen.|
|[/O1](o1-o2-minimize-size-maximize-speed.md)|Erstellt kompakten Code.|
|[/O2](o1-o2-minimize-size-maximize-speed.md)|Erstellt schnellen Code.|
|[/Ob](ob-inline-function-expansion.md)|Steuert Inline-Erweiterung.|
|[/Od](od-disable-debug.md)|Deaktiviert Optimierung.|
|[/Og](og-global-optimizations.md)|Veraltet. Verwendet globale Optimierung.|
|[/Oi](oi-generate-intrinsic-functions.md)|Erstellt systeminterne Funktionen.|
|[/openmp](openmp-enable-openmp-2-0-support.md)|Ermöglicht [#pragma omp](../../preprocessor/omp.md) im Quellcode.|
|[/Os](os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt kompakten Code.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt schnellen Code.|
|[/Ox](ox-full-optimization.md)|Verwendet maximale Optimierung (/Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Unterdrückt Framezeiger (nur x86).|
|[/P](p-preprocess-to-a-file.md)|Schreibt Präprozessorausgaben in eine Datei.|
|[/permissive-](permissive-standards-conformance.md)|Festlegen Sie Standard-Konformität Modus.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Generiert schnelle Transzendente.|
|[/QIfist](qifist-suppress-ftol.md)|Veraltet. Unterdrückt `_ftol` , wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich ist (nur x86).|
|[/Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Entfernt `fwait` -Befehle in `try` -Blöcken.|
|[/Qpar (Automatische Parallelisierung)](qpar-auto-parallelizer.md)|Ermöglicht automatische Parallelisierung von Schleifen, die mit der [#pragma loop()](../../preprocessor/loop.md) -Direktive gekennzeichnet sind.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Verwendet ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.|
|[/Qvec-report (Berichtebene der automatischen Vektorisierung)](qvec-report-auto-vectorizer-reporting-level.md)|Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.|
|[/RTC](rtc-run-time-error-checks.md)|Aktiviert Laufzeitfehlerüberprüfung.|
|[/sdl](sdl-enable-additional-security-checks.md)|Aktiviert zusätzliche Sicherheitsfunktionen und Warnungen.|
|[/showIncludes](showincludes-list-include-files.md)|Zeigt während der Kompilierung eine Liste der Includedateien an.|
|[/source-charset](source-charset-set-source-character-set.md)|Festlegen des quellzeichensatzes.|
|[/std](std-specify-language-standard-version.md)|C++-Standardversion Kompatibilität Selektor.|
|[/Tc](tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C-Quelldatei an.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien C. sind|
|[/Tp](tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C++-Quelldatei an.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien C++ sind.|
|[/U](u-u-undefine-symbols.md)|Entfernt ein vorkompiliertes Makro.|
|[/u](u-u-undefine-symbols.md)|Entfernt alle vorkompilierten Makros.|
|[/utf-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Set Zeichensätze Quell- und in UTF-8.|
|[/V](v-version-number.md)|Veraltet. Legt die Versionszeichenfolge der OBJ-Datei fest.|
|[/validate-charset](validate-charset-validate-for-compatible-characters.md)|Überprüfen Sie die UTF-8-Dateien für nur kompatibel Zeichen.|
|[/vd](vd-disable-construction-displacements.md)|Unterdrückt oder aktiviert ausgeblendete vtordisp-Klassenmember.|
|[/vmb](vmb-vmg-representation-method.md)|Verwendet bestmögliche Basis für Zeiger auf Member.|
|[/vmg](vmb-vmg-representation-method.md)|Verwendet volle Allgemeingültigkeit für Zeiger auf Member.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Deklariert mehrfache Vererbung.|
|[/vms](vmm-vms-vmv-general-purpose-representation.md)|Deklariert einfache Vererbung.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Deklariert virtuelle Vererbung.|
|[/volatile](volatile-volatile-keyword-interpretation.md)|Wählt aus, wie das volatile-Schlüsselwort interpretiert wird.|
|[/w](compiler-option-warning-level.md)|Deaktiviert alle Warnungen.|
|[/W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Legt die auszugebende Warnstufe fest.|
|[/w1, /w2, /w3, /w4](compiler-option-warning-level.md)|Legt die Warnstufe für die angegebene Warnung fest.|
|[/Wall](compiler-option-warning-level.md)|Aktiviert alle Warnungen, einschließlich standardmäßig deaktivierter Warnmeldungen.|
|[/wd](compiler-option-warning-level.md)|Deaktiviert die angegebene Warnung.|
|[/we](compiler-option-warning-level.md)|Behandelt die angegebene Warnung als einen Fehler.|
|[/WL](wl-enable-one-line-diagnostics.md)|Aktiviert einzeilige Diagnose für Fehler- und Warnmeldungen beim Kompilieren von C++-Quellcode aus der Befehlszeile.|
|[/wo](compiler-option-warning-level.md)|Zeigt die angegebene Warnung nur einmal an.|
|[/Wp64](wp64-detect-64-bit-portability-issues.md)|Veraltet. Erkennt 64-Bit-Portabilitätsprobleme.|
|[/Wv](compiler-option-warning-level.md)|Zeigt keine Warnungen an, die nach der angegebenen Version des Compilers eingeführt wurden.|
|[/WX](compiler-option-warning-level.md)|Behandelt alle Warnungen als Fehler.|
|[/X](x-ignore-standard-include-paths.md)|Ignoriert das standardmäßige Includeverzeichnis.|
|[/Y-](y-ignore-precompiled-header-options.md)|Ignoriert alle anderen Optionen für vorkompilierte Header im aktuellen Erstellungsprozess.|
|[/Yc](yc-create-precompiled-header-file.md)|Erstellt eine vorkompilierte Headerdatei.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Veraltet. Legt vollständige Debuginformationen in allen Objektdateien ab. Verwendung [/Zi](z7-zi-zi-debug-information-format.md) stattdessen.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Fügt beim Erstellen einer Debugbibliothek einen PCH-Verweis ein|
|[/Yu](yu-use-precompiled-header-file.md)|Verwendet eine vorkompilierte Headerdatei beim Erstellungsvorgang.|
|[/Z7](z7-zi-zi-debug-information-format.md)|Generiert C 7.0-kompatible Debuginformationen.|
|[/Za](za-ze-disable-language-extensions.md)|Deaktiviert Spracherweiterungen.|
|[/Zc](zc-conformance.md)|Legt Standardverhalten unter ["/ Ze"](za-ze-disable-language-extensions.md).[ / Za, / Ze (Spracherweiterungen deaktivieren)](za-ze-disable-language-extensions.md)|
|[/Ze](za-ze-disable-language-extensions.md)|Veraltet. Aktiviert Spracherweiterungen.|
|[/Zf](zf.md)|Verbessert die PDB-Datei bei der parallelen Builderstellung Ereigniserzeugung.|
|[/Zg](zg-generate-function-prototypes.md)|In Visual C++ 2015 entfernt. Erzeugt Funktionsprototypen.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Fügt Debuginformationen in eine Programmdatenbank ein, die mit Bearbeiten und Fortfahren kompatibel ist.|
|[/Zi](z7-zi-zi-debug-information-format.md)|Erzeugt vollständige Debuginformationen.|
|[/Zl](zl-omit-default-library-name.md)|Entfernt Standard-Bibliotheksnamen aus der OBJ-Datei (nur x86).|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Legt die maximale Speicherbelegung für den vorkompilierten Header fest.|
|[/Zp](zp-struct-member-alignment.md)|Komprimiert Strukturmember.|
|[/Zs](zs-syntax-check-only.md)|Prüft nur die Syntax.|
|[/ZW](zw-windows-runtime-compilation.md)|Erzeugt eine Ausgabedatei, die auf Windows-Runtime ausgeführt werden.|

## <a name="see-also"></a>Siehe auch
 [Referenz zur C/C++-Erstellung](c-cpp-building-reference.md) [Compileroptionen](compiler-options.md) [Festlegen von Compileroptionen](setting-compiler-options.md)