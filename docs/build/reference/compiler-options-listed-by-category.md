---
title: Compileroptionen nach Kategorien sortiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
caps.latest.revision: "64"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec2b8f0f05da535fd6a4f212a08af847c997a860
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-options-listed-by-category"></a>Compileroptionen nach Kategorien sortiert
Dieser Artikel enthält eine nach Kategorien sortierte Liste der Compileroptionen. Eine alphabetische Liste finden Sie unter [Compiler Options Listed Alphabetically](../../build/reference/compiler-options-listed-alphabetically.md).  
  
### <a name="optimization"></a>Optimierung  
  
|Option|Zweck|  
|------------|-------------|  
|[/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Erstellt kompakten Code.|  
|[/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)|Erstellt schnellen Code.|  
|[/Ob](../../build/reference/ob-inline-function-expansion.md)|Steuert Inline-Erweiterung.|  
|[/Od](../../build/reference/od-disable-debug.md)|Deaktiviert Optimierung.|  
|[/Og](../../build/reference/og-global-optimizations.md)|Veraltet. Verwendet globale Optimierung.|  
|[/Oi](../../build/reference/oi-generate-intrinsic-functions.md)|Erstellt systeminterne Funktionen.|  
|[/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt kompakten Code.|  
|[/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)|Bevorzugt schnellen Code.|  
|[/Ox](../../build/reference/ox-full-optimization.md)|Verwendet maximale Optimierung (/Ob2gity /Gs).|  
|[/Oy](../../build/reference/oy-frame-pointer-omission.md)|Unterdrückt Framezeiger. (nur x86)|  
|[/favor](../../build/reference/favor-optimize-for-architecture-specifics.md)|Erzeugt Code, der für eine bestimmte Architektur optimiert wird, oder für einen Bereich von Architekturen.|  
  
### <a name="code-generation"></a>Codeerzeugung  
  
|Option|Zweck|  
|------------|-------------|  
|[/arch](../../build/reference/arch-x86.md)|Verwendet SSE- oder SSE2-Anweisungen bei der Codeerzeugung. (nur x86)|  
|[/clr](../../build/reference/clr-common-language-runtime-compilation.md)|Erzeugt eine Ausgabedatei, die auf der Common Language Runtime ausgeführt werden kann.|  
|[/EH](../../build/reference/eh-exception-handling-model.md)|Gibt das Modell der Ausnahmebehandlung an.|  
|[/fp](../../build/reference/fp-specify-floating-point-behavior.md)|Gibt das Gleitkommaverhalten an.|  
|[/GA](../../build/reference/ga-optimize-for-windows-application.md)|Optimiert Windows-Anwendungen.|  
|[/Gd](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Verwendet die `__cdecl` -Aufrufkonvention. (nur x86)|  
|[/Ge](../../build/reference/ge-enable-stack-probes.md)|Veraltet. Aktiviert Stapelüberprüfungen.|  
|[/GF](../../build/reference/gf-eliminate-duplicate-strings.md)|Aktiviert Stringpooling.|  
|[/Gh](../../build/reference/gh-enable-penter-hook-function.md)|Ruft die Hookfunktion `_penter`auf.|  
|[/GH](../../build/reference/gh-enable-pexit-hook-function.md)|Ruft die Hookfunktion `_pexit`auf.|  
|[/GL](../../build/reference/gl-whole-program-optimization.md)|Aktiviert die Optimierung des gesamten Programms.|  
|[/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Aktiviert minimale Neuerstellung.|  
|[/GR](../../build/reference/gr-enable-run-time-type-information.md)|Aktiviert Laufzeit-Typeninformation (RTTI).|  
|[/Gr](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Verwendet die `__fastcall` -Aufrufkonvention. (nur x86)|  
|[/GS](../../build/reference/gs-buffer-security-check.md)|Überprüft die Puffersicherheit.|  
|[/Gs](../../build/reference/gs-control-stack-checking-calls.md)|Steuert Stapelüberprüfungen|  
|[/GT](../../build/reference/gt-support-fiber-safe-thread-local-storage.md)|Unterstützt Fiber-Sicherheit für Daten, die mit statischem lokalen Threadspeicher zugewiesen werden.|  
|[/guard:cf](../../build/reference/guard-enable-control-flow-guard.md)|Fügt Sicherheitsüberprüfungen zum Ablaufsteuerungsschutz hinzu.|  
|[/Gv](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Verwendet die `__vectorcall` -Aufrufkonvention. (nur x86 und x64)|  
|[/Gw](../../build/reference/gw-optimize-global-data.md)|Ermöglicht programmübergreifende globale Datenoptimierung.|  
|[/GX](../../build/reference/gx-enable-exception-handling.md)|Veraltet. Aktiviert synchrone Ausnahmebehandlung. Verwenden Sie stattdessen [/EH](../../build/reference/eh-exception-handling-model.md) .|  
|[/Gy](../../build/reference/gy-enable-function-level-linking.md)|Aktiviert Funktionslevel-Linking.|  
|[/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Veraltet. Ermöglicht schnelle Überprüfungen. (Entspricht [/RTC1](../../build/reference/rtc-run-time-error-checks.md).)|  
|[/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md)|Verwendet die `__stdcall` -Aufrufkonvention. (nur x86)|  
|[/homeparams](../../build/reference/homeparams-copy-register-parameters-to-stack.md)|Erzwingt, dass in Registern übergebene Parameter beim Funktionseinstieg in ihre Speicherorte auf dem Stapel geschrieben werden. Diese Compileroption gilt nur für die [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Compiler (systemeigene und Cross-Compiler).|  
|[/hotpatch](../../build/reference/hotpatch-create-hotpatchable-image.md)|Erstellt ein Hotpatch-fähiges Abbild.|  
|[/Qfast_transcendentals](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md)|Generiert schnelle Transzendente.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Veraltet. Unterdrückt den Aufruf der `_ftol` -Hilfsfunktion, wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich ist. (nur x86)|  
|[/Qimprecise_fwaits](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Entfernt `fwait` -Befehle in `try` -Blöcken.|  
|[/Qpar](../../build/reference/qpar-auto-parallelizer.md)|Ermöglicht automatische Parallelisierung von Schleifen.|  
|[/Qpar-report](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)|Aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.|  
|[/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md)|Verwendet ganzzahlige Verschiebungsanweisungen für Gleitkommawerte und deaktiviert bestimmte Gleitkomma-Ladeoptimierungen.|  
|[/ Qvec-Report-(Auto-Vektorisierer Berichtsebene)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md)|Aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.|  
|[/RTC](../../build/reference/rtc-run-time-error-checks.md)|Aktiviert Laufzeitfehlerüberprüfung.|  
|[/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md)|Wählt aus, wie das volatile-Schlüsselwort interpretiert wird.|  
  
### <a name="output-files"></a>Ausgabedateien  
  
|Option|Zweck|  
|------------|-------------|  
|[/doc](../../build/reference/doc-process-documentation-comments-c-cpp.md)|Verarbeitet Dokumentationskommentare zu einer XML-Datei.|  
|[/FA](../../build/reference/fa-fa-listing-file.md)|Konfiguriert eine Assemblylistendatei.|  
|[/Fa](../../build/reference/fa-fa-listing-file.md)|Erstellt eine Assemblylistendatei.|  
|[/Fd](../../build/reference/fd-program-database-file-name.md)|Benennt die Programmdatenbankdatei um.|  
|[/Fe](../../build/reference/fe-name-exe-file.md)|Benennt die ausführbare Datei um.|  
|[/Fi](../../build/reference/fi-preprocess-output-file-name.md)|Gibt den Namen der vorverarbeiteten Ausgabedatei an.|  
|[/Fm](../../build/reference/fm-name-mapfile.md)|Erstellt eine Zuordnungsdatei.|  
|[/Fo](../../build/reference/fo-object-file-name.md)|Erstellt eine Objektdatei.|  
|[/Fp](../../build/reference/fp-name-dot-pch-file.md)|Gibt den Namen einer vorkompilierten Headerdatei an.|  
|[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Erstellt Browserdateien.|  
  
### <a name="preprocessor"></a>Präprozessor  
  
|Option|Zweck|  
|------------|-------------|  
|[/AI](../../build/reference/ai-specify-metadata-directories.md)|Gibt das zu durchsuchende Verzeichnis an, um Dateiverweise aufzulösen, die an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben wurden.|  
|[/C](../../build/reference/c-preserve-comments-during-preprocessing.md)|Behält Kommentare beim Präprozessorlauf bei|  
|[/D](../../build/reference/d-preprocessor-definitions.md)|Definiert Konstanten und Makros.|  
|[/E](../../build/reference/e-preprocess-to-stdout.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|  
|[/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Kopiert die Präprozessorausgabe in die Standardausgabe.|  
|[/FI](../../build/reference/fi-name-forced-include-file.md)|Führt eine Vorverarbeitung der angegebenen Includedatei durch.|  
|[/FU](../../build/reference/fu-name-forced-hash-using-file.md)|Erzwingt die Verwendung eines Dateinamens, als ob er an die [#using](../../preprocessor/hash-using-directive-cpp.md) -Direktive übergeben worden wäre.|  
|[/Fx](../../build/reference/fx-merge-injected-code.md)|Führt eingefügten Code mit der Quelldatei zusammen.|  
|[/I](../../build/reference/i-additional-include-directories.md)|Sucht in einem Verzeichnis nach Includedateien.|  
|[/P](../../build/reference/p-preprocess-to-a-file.md)|Schreibt Präprozessorausgaben in eine Datei.|  
|[/U](../../build/reference/u-u-undefine-symbols.md)|Entfernt ein vorkompiliertes Makro.|  
|[/u](../../build/reference/u-u-undefine-symbols.md)|Entfernt alle vorkompilierten Makros.|  
|[/X](../../build/reference/x-ignore-standard-include-paths.md)|Ignoriert das standardmäßige Includeverzeichnis.|  
  
### <a name="language"></a>Sprache  
  
|Option|Zweck|  
|------------|-------------|  
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Constexpr-Auswertung zum Zeitpunkt der Kompilierung zu steuern.|  
|[/openmp](../../build/reference/openmp-enable-openmp-2-0-support.md)|Ermöglicht [#pragma omp](../../preprocessor/omp.md) im Quellcode.|  
|[/vd](../../build/reference/vd-disable-construction-displacements.md)|Unterdrückt oder aktiviert ausgeblendete `vtordisp` -Klassenmember.|  
|[/vmb](../../build/reference/vmb-vmg-representation-method.md)|Verwendet bestmögliche Basis für Zeiger auf Member.|  
|[/vmg](../../build/reference/vmb-vmg-representation-method.md)|Verwendet volle Allgemeingültigkeit für Zeiger auf Member.|  
|[/vmm](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Deklariert mehrfache Vererbung.|  
|[/vms](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Deklariert einfache Vererbung.|  
|[/vmv](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)|Deklariert virtuelle Vererbung.|  
|[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)|Generiert C 7.0-kompatible Debuginformationen.|  
|[/Za](../../build/reference/za-ze-disable-language-extensions.md)|Deaktiviert Spracherweiterungen.|  
|[/Zc](../../build/reference/zc-conformance.md)|Legt Standardverhalten unter [/Ze](../../build/reference/za-ze-disable-language-extensions.md)fest.|  
|[/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Veraltet. Aktiviert Spracherweiterungen.|  
|[/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)|Fügt Debuginformationen in eine Programmdatenbank ein, die mit Bearbeiten und Fortfahren kompatibel ist. (nur x86)|  
|[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)|Erzeugt vollständige Debuginformationen.|  
|[/Zl](../../build/reference/zl-omit-default-library-name.md)|Entfernt den Standardbibliotheksnamen aus der OBJ-Datei.|  
|[/Zp](../../build/reference/zp-struct-member-alignment.md) *n*|Komprimiert Strukturmember.|  
|[/Zs](../../build/reference/zs-syntax-check-only.md)|Prüft nur die Syntax.|  
|[/ZW](../../build/reference/zw-windows-runtime-compilation.md)|Erzeugt eine Ausgabedatei, die auf Windows-Runtime ausgeführt werden.|  
  
### <a name="linking"></a>Verknüpfen  
  
|Option|Zweck|  
|------------|-------------|  
|[/F](../../build/reference/f-set-stack-size.md)|Legt die Stapelgröße fest.|  
|[/LD](../../build/reference/md-mt-ld-use-run-time-library.md)|Erstellt eine Dynamic Link Library (DLL).|  
|[/LDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Erstellt eine Debug-Dynamic Link Library.|  
|[/link](../../build/reference/link-pass-options-to-linker.md)|Übergibt die angegebene Option an LINK.|  
|[/LN](../../build/reference/ln-create-msil-module.md)|Generiert ein MSIL-Modul.|  
|[/MD](../../build/reference/md-mt-ld-use-run-time-library.md)|Kompiliert, um mit MSVCRT.LIB eine Multithread-DLL zu erstellen.|  
|[/MDd](../../build/reference/md-mt-ld-use-run-time-library.md)|Kompiliert, um mit MSVCRTD.LIB eine Multithread-DLL für den Debugger zu erstellen.|  
|[/MT](../../build/reference/md-mt-ld-use-run-time-library.md)|Kompiliert, um mit LIBCMT.LIB eine ausführbare Multithreaddatei zu erstellen.|  
|[/MTd](../../build/reference/md-mt-ld-use-run-time-library.md)|Kompiliert, um mit LIBCMTD.LIB eine ausführbare Multithreaddatei für den Debugger zu erstellen.|  
  
### <a name="miscellaneous"></a>Verschiedenes  
  
|Option|Zweck|  
|------------|-------------|  
|[/?](../../build/reference/help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|  
|[@](../../build/reference/at-specify-a-compiler-response-file.md)|Legt eine Antwortdatei fest.|  
|[/analyze](../../build/reference/analyze-code-analysis.md)|Aktiviert die Codeanalyse.|  
|[/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)|Erhöht die Anzahl von adressierbaren Abschnitten in einer OBJ-Datei.|  
|[/c](../../build/reference/c-compile-without-linking.md)|Kompiliert ohne Verknüpfen.|  
|[/cgthreads](../../build/reference/cgthreads-code-generation-threads.md)|Gibt die Anzahl der cl.exe-Threads an, die für Optimierung und Codegenerierung verwendet werden.|  
|[/errorReport](../../build/reference/errorreport-report-internal-compiler-errors.md)|Ermöglicht Ihnen, Informationen über interne Compilerfehler direkt an das Visual C++-Team zu senden.|  
|[/FC](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)|Zeigt den vollständigen Pfad der Quellcodedateien im Diagnosetext in CL.EXE an.|  
|[/FS](../../build/reference/fs-force-synchronous-pdb-writes.md)|Erzwingt die Serialisierung von Schreibvorgängen auf die Programmdatenbank (PDB) mithilfe von MSPDBSRV.EXE.|  
|[/H](../../build/reference/h-restrict-length-of-external-names.md)|Veraltet. Beschränkt die Länge externer (öffentlicher) Namen.|  
|[/HELP](../../build/reference/help-compiler-command-line-help.md)|Listet die Compileroptionen auf.|  
|[/J](../../build/reference/j-default-char-type-is-unsigned.md)|Ändert den `char` -Standardtyp.|  
|[/kernel](../../build/reference/kernel-create-kernel-mode-binary.md)|Der Compiler und der Linker erstellen eine Binärdatei, die im Kernel von Windows ausgeführt werden kann.|  
|[/MP](../../build/reference/mp-build-with-multiple-processes.md)|Erstellt mehrere Quelldateien gleichzeitig.|  
|[/nologo](../../build/reference/nologo-suppress-startup-banner-c-cpp.md)|Unterdrückt die Anzeige von Startinformationen.|  
|[/sdl](../../build/reference/sdl-enable-additional-security-checks.md)|Aktiviert zusätzliche Sicherheitsfunktionen und Warnungen.|  
|[/showIncludes](../../build/reference/showincludes-list-include-files.md)|Zeigt während der Kompilierung eine Liste aller Includedateien an.|  
|[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C-Quelldatei an.|  
|[/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien C. sind|  
|[/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Gibt eine C++-Quelldatei an.|  
|[/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)|Gibt an, dass alle Quelldateien C++ sind.|  
|[/V](../../build/reference/v-version-number.md)|Veraltet. Legt die Versionszeichenfolge fest.|  
|[/w](../../build/reference/compiler-option-warning-level.md)|Deaktiviert alle Warnungen.|  
|[/W0, /W1, /W2, /W3, /W4](../../build/reference/compiler-option-warning-level.md)|Legt die ausgegebene Warnstufe fest.|  
|[/w1, /w2, /w3, /w4](../../build/reference/compiler-option-warning-level.md)|Legt die Warnstufe für die angegebene Warnung fest.|  
|[/Wall](../../build/reference/compiler-option-warning-level.md)|Aktiviert alle Warnungen, einschließlich standardmäßig deaktivierter Warnmeldungen.|  
|[/wd](../../build/reference/compiler-option-warning-level.md)|Deaktiviert die angegebene Warnung.|  
|[/we](../../build/reference/compiler-option-warning-level.md)|Behandelt die angegebene Warnung als einen Fehler.|  
|[/WL](../../build/reference/wl-enable-one-line-diagnostics.md)|Aktiviert einzeilige Diagnose für Fehler- und Warnmeldungen beim Kompilieren von C++-Quellcode aus der Befehlszeile.|  
|[/wo](../../build/reference/compiler-option-warning-level.md)|Zeigt die angegebene Warnung nur einmal an.|  
|[/Wv](../../build/reference/compiler-option-warning-level.md)|Deaktiviert die Warnungen, die durch spätere Versionen des Compilers eingeführt wurden.|  
|[/WX](../../build/reference/compiler-option-warning-level.md)|Behandelt Warnungen wie Fehler.|  
|[/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Erstellen. PCH-Datei.|  
|[/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Veraltet. Legt vollständige Debuginformationen in allen Objektdateien ab. Verwenden Sie stattdessen [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) .|  
|[/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)|Fügt beim Erstellen einer Debugbibliothek einen PCH-Verweis ein.|  
|[/Yu](../../build/reference/yu-use-precompiled-header-file.md)|Verwendet eine vorkompilierte Headerdatei beim Erstellungsvorgang.|  
|[/Y-](../../build/reference/y-ignore-precompiled-header-options.md)|Ignoriert alle anderen Optionen für vorkompilierte Header im aktuellen Erstellungsprozess.|  
|[/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)|Legt die maximale Speicherbelegung für den vorkompilierten Header fest.|  
|[/ "await"](await-enable-coroutine-support.md)|Aktivieren Sie Erweiterungen für Coroutinen (fortsetzbare Funktionen).|  
|[/Source-CharSet](source-charset-set-source-character-set.md)|Festlegen des quellzeichensatzes.|
|[/Execution-CharSet](execution-charset-set-execution-character-set.md)|Der ausführungszeichensatz festlegen.|
|[/UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Set Zeichensätze Quell- und in UTF-8.|
|[/Validate-CharSet](validate-charset-validate-for-compatible-characters.md)|Überprüfen Sie die UTF-8-Dateien für nur kompatibel Zeichen.|
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Steuert das Format der diagnosemeldungen an.|
|[/ liberalen-](permissive-standards-conformance.md)|Festlegen Sie Standard-Konformität Modus.|
|[/Std](std-specify-language-standard-version.md)|C++-Standardversion Kompatibilität Selektor.|
  
### <a name="deprecated-and-removed-compiler-options"></a>Veraltete und entfernte Compileroptionen  
  
|Option|Zweck|  
|------------|-------------|  
|[/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md)|Veraltet. Verwenden Sie stattdessen [/LN (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) .|  
|[/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)|Veraltet. Erstellt eine Browseinformationsdatei ohne lokale Variablen.|  
|[/Ge](../../build/reference/ge-enable-stack-probes.md)|Veraltet. Aktiviert Stapelüberprüfungen. Standardmäßig aktiviert.|  
|[/GX](../../build/reference/gx-enable-exception-handling.md)|Veraltet. Aktiviert synchrone Ausnahmebehandlung. Verwenden Sie stattdessen [/EH](../../build/reference/eh-exception-handling-model.md) .|  
|[/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)|Veraltet. Ermöglicht schnelle Überprüfungen. Verwenden Sie stattdessen [/RTC1](../../build/reference/rtc-run-time-error-checks.md) .|  
|[/H](../../build/reference/h-restrict-length-of-external-names.md)|Veraltet. Beschränkt die Länge externer (öffentlicher) Namen.|  
|[/Og](../../build/reference/og-global-optimizations.md)|Veraltet. Verwendet globale Optimierung.|  
|[QIfist](../../build/reference/qifist-suppress-ftol.md)|Veraltet. Wurde verwendet, um anzugeben, wie aus einem Gleitkommatyp in einen ganzzahligen Typ konvertiert werden soll.|  
|[/V](../../build/reference/v-version-number.md)|Veraltet. Legt die Versionszeichenfolge der OBJ-Datei fest.|  
|[/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md)|Veraltet. Erkennt 64-Bit-Portabilitätsprobleme.|  
|[/Yd](../../build/reference/yd-place-debug-information-in-object-file.md)|Veraltet. Legt vollständige Debuginformationen in allen Objektdateien ab. Verwenden Sie stattdessen [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) .|  
|[/Zc:forScope-](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)|Veraltet. Deaktiviert Übereinstimmung in einem for-Schleifenbereich.|  
|[/Ze](../../build/reference/za-ze-disable-language-extensions.md)|Veraltet. Aktiviert Spracherweiterungen.|  
|[/Zg](../../build/reference/zg-generate-function-prototypes.md)|In Visual C++ 2015 entfernt. Erzeugt Funktionsprototypen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)