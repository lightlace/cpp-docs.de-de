---
title: "Linkeroptionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bibliotheken [C++], Verknüpfen mit COFF"
  - "LINK-Tool [C++], Linkeroptionen"
  - "Linker [C++]"
  - "Linker [C++], Aufgelistete Optionen"
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
caps.latest.revision: 37
caps.handback.revision: "35"
ms.author: "corob"
manager: "ghogen"
---
# Linkeroptionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"LINK.exe" ist ein Tool, das Objektdateien und Bibliotheken im COFF\-Format \(Common Object File Format\) miteinander verbindet, um eine ausführbare Datei \(EXE\-Datei\) oder eine DLL \(Dynamic Link Library\) zu erstellen.  
  
 In der folgenden Tabelle sind die Optionen für "LINK.exe" aufgelistet. Weitere Informationen zu LINK finden Sie unter:  
  
-   [LINK\-Optionen, die über den Compiler gesteuert werden](../../build/reference/compiler-controlled-link-options.md)  
  
-   [LINK\-Eingabedateien](../../build/reference/link-input-files.md)  
  
-   [LINK\-Ausgabe](../../build/reference/link-output.md)  
  
-   [Reservierte Wörter](../../build/reference/reserved-words.md)  
  
 An der Befehlszeile werden Linkeroptionen nicht nach Groß\- und Kleinschreibung unterschieden, so sind zum Beispiel "\/base" und "\/BASE" gleichbedeutend. Anweisungen zum Angeben der einzelnen Optionen in der Befehlszeile oder in Visual Studio finden Sie in der Dokumentation zur entsprechenden Option.  
  
 Einige Linkeroptionen können Sie auch mit dem [comment](../../preprocessor/comment-c-cpp.md)\-Pragma festlegen.  
  
|Option|Zweck|  
|------------|-----------|  
|[@](../../build/reference/at-specify-a-linker-response-file.md)|Legt eine Antwortdatei fest.|  
|[\/ALIGN](../../build/reference/align-section-alignment.md)|Legt die Ausrichtung eines Abschnitts fest.|  
|[\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|Legt fest, dass keine DLLs verknüpft werden können.|  
|[\/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|Gibt das Verhalten bei der Manifestsuche an.|  
|[\/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|Gibt an, ob die App in einer appcontainer\-Prozessumgebung ausgeführt werden muss.|  
|[\/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)|Fügt einem verwalteten Image das <xref:System.Diagnostics.DebuggableAttribute> hinzu.|  
|[\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|Erstellt einen Link zu einer verwalteten Ressource.|  
|[\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|Legt fest, dass ein MSIL\-Modul \(Microsoft Intermediate Language\) in den Assembler importiert werden soll.|  
|[\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|Bettet eine verwaltete Ressourcendatei in eine Assembly ein.|  
|[\/BASE](../../build/reference/base-base-address.md)|Legt eine Basisadresse für das Programm fest.|  
|[\/CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|Legt die Anzahl von cl.exe\-Threads zur Verwendung für die Optimierung und Codegenerierung fest, wenn die Link\-Zeitcodegenerierung angegeben ist.|  
|[\/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)|Legt den Typ \(IJW, rein oder sicher\) eines CLR\-Images fest.|  
|[\/CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|Behält den letzten Fehlercode von Funktionen bei, die vom P\/Invoke\-Mechanismus aufgerufen werden.|  
|[\/CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|Gibt das Threadingattribut an, das auf den Einstiegspunkt des CLR\-Programms angewendet wird.|  
|[\/CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute.md)|Gibt an, ob der Linker das SuppressUnmanagedCodeSecurity\-Attribute auf vom Linker generierte PInvoke\-Stub, die von verwaltetem Code aus systemeigene DLLs Aufrufen, anwendet.|  
|[\/DEBUG](../../build/reference/debug-generate-debug-info.md)|Erstellt Debuginformationen.|  
|[\/DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|Gibt an, welche Daten in Debuginformationen eingeschlossen werden sollen.|  
|[\/DEF](../../build/reference/def-specify-module-definition-file.md)|Übergibt eine Moduldefinitionsdatei \(DEF\-Datei\) an den Linker.|  
|[\/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|Durchsucht die angegebene Bibliothek beim Auflösen externer Verweise.|  
|[\/DELAY](../../build/reference/delay-delay-load-import-settings.md)|Steuert das verzögerte Laden von DLLs.|  
|[\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|Löst das verzögerte Laden der angegebenen DLL aus.|  
|[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|Eine Assembly wird teilweise signiert.|  
|[\/DLL](../../build/reference/dll-build-a-dll.md)|Erstellt eine DLL.|  
|[\/DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|Erstellt einen Kernelmodustreiber.|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|Gibt an, ob ein ausführbares Image generiert werden soll, für das zur Ladezeit mit der ASLR \(Address Space Layout Randomization\)\-Funktion nach dem Zufallsprinzip ein Rebase\-Vorgang ausgeführt werden kann.|  
|[\/ENTRY](../../build/reference/entry-entry-point-symbol.md)|Legt die Startadresse fest.|  
|[\/errorReport](../../build/reference/errorreport-report-internal-linker-errors.md)|Gibt interne Linkerfehler an Microsoft weiter.|  
|[\/EXPORT](../../build/reference/export-exports-a-function.md)|Exportiert eine Funktion.|  
|[\/FIXED](../../build/reference/fixed-fixed-base-address.md)|Erstellt ein Programm, das nur an seiner bevorzugten Basisadresse geladen werden kann.|  
|[\/FORCE](../../build/reference/force-force-file-output.md)|Erzwingt die Fertigstellung des Links, auch wenn nicht aufgelöste oder mehrfach definierte Symbole vorliegen.|  
|[\/FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|Erstellt ein Hotpatch\-fähiges Image.|  
|[\/GENPROFILE, \/FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Beide Optionen geben die Generierung einer PGD\-Datei durch den Linker an, um die profilgesteuerte Optimierung \(PGO\) zu unterstützen. \/GENPROFILE und \/FASTGENPROFILE verwenden unterschiedliche Standardparameter.|  
|[\/GUARD](../../build/reference/guard-enable-guard-checks.md)|Aktiviert den Ablaufsteuerungsschutz.|  
|[\/HEAP](../../build/reference/heap-set-heap-size.md)|Legt die Größe des Heap in Bytes fest.|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md)|Gibt die Unterstützung für 64\-Bit\-ASLR \(Address Space Layout Randomization\) mit hoher Entropie an.|  
|[\/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)|Legt den Namen der IDL\-Datei und anderer MIDL\-Ausgabedateien fest.|  
|[\/IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|Unterdrückt die Ausgabe der angegebenen Linkerwarnungen.|  
|[\/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|Verhindert die Verarbeitung von Attributinformationen in eine IDL\-Datei.|  
|[\/IMPLIB](../../build/reference/implib-name-import-library.md)|Überschreibt den Standardnamen für die Importbibliothek.|  
|[\/INCLUDE](../../build/reference/include-force-symbol-references.md)|Erzwingt Symbolverweise.|  
|[\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|Steuert inkrementelles Verknüpfen.|  
|[\/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|Gibt an, dass für das Modul eine Signaturüberprüfung zur Ladezeit erforderlich ist.|  
|[\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Gibt einen Schlüsselcontainer zum Signieren einer Assembly an.|  
|[\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Gibt einen Schlüssel oder ein Schlüsselpaar zum Signieren einer Assembly an.|  
|[\/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|Teilt dem Compiler mit, dass die Anwendung Adressen unterstützt, die mehr als zwei Gigabytes umfassen|  
|[\/LIBPATH](../../build/reference/libpath-additional-libpath.md)|Gibt einen Suchpfad vor dem Umgebungsbibliothekspfads an.|  
|[\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|Gibt Link\-Zeitcodegenerierung an.|  
|[\/MACHINE](../../build/reference/machine-specify-target-platform.md)|Legt die Zielplattform fest.|  
|[\/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|Erstellt eine parallele Manifestdatei und bettet sie optional in der Binärdatei ein.|  
|[\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|Legt einen \<dependentAssembly\>\-Abschnitt in der Manifestdatei fest.|  
|[\/MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|Ändert den Standardnamen der Manifestdatei.|  
|[\/MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|Gibt eine Manifesteingabedatei an, die der Linker verarbeitet und in der Binärdatei einbettet. Sie können diese Option mehrmals verwenden, um mehr als eine Manifesteingabedatei anzugeben.|  
|[\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|Gibt an, ob Informationen zur Benutzerkontensteuerung \(UAC\) in das Programmmanifest eingebettet werden.|  
|[\/MAP](../../build/reference/map-generate-mapfile.md)|Erstellt eine Zuordnungsdatei.|  
|[\/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|Fügt die angegebenen Informationen in die Zuordnungsdatei ein.|  
|[\/MERGE](../../build/reference/merge-combine-sections.md)|Kombiniert Abschnitte miteinander.|  
|[\/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|Gibt die MIDL\-Befehlszeilenoptionen an.|  
|[\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|Unterdrückt die Erstellung einer .NET Framework\-Assembly.|  
|[\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|Ignoriert alle \(angegebenen\) Standardbibliotheken bei der Auflösung von externen Verweisen.|  
|[\/NOENTRY](../../build/reference/noentry-no-entry-point.md)|Erstellt eine DLL, die nur als Ressource dient.|  
|[\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|Unterdrückt den Startbanner.|  
|[\/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Kennzeichnet eine ausführbare Datei als mit der Windows\-Funktion zur Datenausführungsverhinderung kompatibel.|  
|[\/OPT](../../build/reference/opt-optimizations.md)|Steuert die LINK\-Optimierungen.|  
|[\/ORDER](../../build/reference/order-put-functions-in-order.md)|Fügt COMDATs in einer vordefinierten Reihenfolge in das Image ein.|  
|[\/OUT](../../build/reference/out-output-file-name.md)|Gibt den Ausgabedateinamen an.|  
|[\/PDB](../../build/reference/pdb-use-program-database.md)|Erstellt eine Programmdatenbankdatei \(PDB\-Datei\).|  
|[\/PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|Verwendet einen alternativen Speicherort zum Speichern einer PDB\-Datei.|  
|[\/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|Erstellt eine Programmdatenbankdatei \(PDB\-Datei\) ohne eigene Symbole.|  
|[\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|Gibt die PGD\-Datei für profilgesteuerte Optimierungen an.|  
|[\/PROFILE](../../build/reference/profile-performance-tools-profiler.md)|Erstellt eine Ausgabedatei, die mit dem Leistungstoolprofiler verwendet werden kann.|  
|[\/RELEASE](../../build/reference/release-set-the-checksum.md)|Legt die Prüfsumme im Header der EXE\-Datei fest.|  
|[\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)|Legt fest, dass das Image eine Tabelle mit sicheren Ausnahmehandlern enthält.|  
|[\/SECTION](../../build/reference/section-specify-section-attributes.md)|Überschreibt die Attribute eines Abschnitts.|  
|[\/STACK](../../build/reference/stack-stack-allocations.md)|Legt die Stapelgröße in Bytes fest.|  
|[\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|Fügt ein MS\-DOS\-Stubprogramm an ein Win32\-Programm an.|  
|[\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|Teilt dem Betriebssystem mit, wie die EXE\-Datei auszuführen ist.|  
|[\/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|Weist das Betriebssystem an, die Linkerausgabe vor dem Ausführen in eine Auslagerungsdatei zu kopieren.|  
|[\/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|Gibt Ressourcen\-ID der vom Linker generierten Typbibliothek an.|  
|[\/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|Legt den Namen der TLB\-Datei und anderer MIDL\-Ausgabedateien fest.|  
|[\/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|Erstellt eine Anwendung, die auf dem Terminalserver ausgeführt werden soll.|  
|[\/VERBOSE](../../build/reference/verbose-print-progress-messages.md)|Druckt Linkerstatusmeldungen aus.|  
|[\/VERSION](../../build/reference/version-version-information.md)|Weist eine Versionsnummer zu.|  
|[\/WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Aktiviert die Generierung einer Windows\-Runtime\-Metadatendatei.|  
|[\/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)|Gibt den Dateinamen für die Ausgabedatei der Windows\-Runtime\-Metadaten \(winmd\) an, die von der [\/WINMD](../../build/reference/winmd-generate-windows-metadata.md)\- Linkeroption generiert wird.|  
|[\/WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Gibt einen Schlüssel oder ein Schlüsselpaar an, um eine Windows\-Runtime\-Metadatendatei zu signieren.|  
|[\/WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Gibt einen Schlüsselcontainer zum Signieren einer Windows\-Metadatendatei an.|  
|[\/WINMDDELAYSIGN](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|Signiert teilweise eine Windows\-Runtime\-Metadatendatei \(.winmd\), indem der öffentliche Schlüssels in die winmd\-Datei eingefügt wird.|  
|[\/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|Behandelt Linkerwarnungen als Fehler.|  
  
 Weitere Informationen finden Sie unter [LINK\-Optionen, die über den Compiler gesteuert werden](../../build/reference/compiler-controlled-link-options.md).  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Häufig gestellte Fragen \(FAQs\) zur Erstellung](assetId:///56a3bb8f-0181-4989-bab4-a07ba950ab08)