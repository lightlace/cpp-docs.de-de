# [C-Laufzeitbibliotheksreferenz](c-run-time-library-reference.md)
# [CRT-Bibliotheksfunktionen](crt-library-features.md)
## [Kompatibilität](compatibility.md)
### [Windows Store-Apps, die Windows-Runtime und die C-Laufzeit](windows-store-apps-the-windows-runtime-and-the-c-run-time.md)
### [ANSI C-Kompatibilität](ansi-c-compliance.md)
### [UNIX](unix.md)
### [Windows-Plattformen (CRT)](windows-platforms-crt.md)
### [Abwärtskompatibilität](backward-compatibility.md)
## [Erforderliche und optionale Headerdateien](required-and-optional-header-files.md)
## [Dateien und Streams](files-and-streams.md)
### [Text- und binäre Streams](text-and-binary-streams.md)
### [Byte- und weite Streams](byte-and-wide-streams.md)
### [Steuern von Streams](controlling-streams.md)
### [Streamzustände](stream-states.md)
## [Empfehlungen für die Wahl zwischen Funktionen und Macros](recommendations-for-choosing-between-functions-and-macros.md)
## [Typüberprüfung (CRT)](type-checking-crt.md)
## [Richtungskennzeichen](direction-flag.md)
## [Sicherheitsfunktionen in der CRT](security-features-in-the-crt.md)
### [CRT-Funktionsversionen mit erweiterter Sicherheit](security-enhanced-versions-of-crt-functions.md)
### [Parametervalidierung](parameter-validation.md)
### [Sichere Vorlagenüberladungen](secure-template-overloads.md)
## [SAL-Anmerkungen](sal-annotations.md)
## [Leistung von Multithreadbibliotheken](multithreaded-libraries-performance.md)
## [Linkoptionen](link-options.md)
## [Potenzielle Fehler bei der Übergabe von CRT-Objekten über DLL-Grenzen](potential-errors-passing-crt-objects-across-dll-boundaries.md)
## [CRT-Initialisierung](crt-initialization.md)
# [Laufzeitroutinen nach Kategorie](run-time-routines-by-category.md)
## [Argumentzugriff](argument-access.md)
## [Pufferbearbeitung](buffer-manipulation.md)
## [Byteklassifizierung](byte-classification.md)
## [Zeichenklassifizierung](character-classification.md)
## [Datenausrichtung](data-alignment.md)
## [Datenkonvertierung](data-conversion.md)
## [Debugroutinen](debug-routines.md)
## [Verzeichnissteuerung](directory-control.md)
## [Fehlerbehandlung (CRT)](error-handling-crt.md)
## [Ausnahmebehandlungsroutinen](exception-handling-routines.md)
## [Dateibehandlung](file-handling.md)
## [Gleitkommaunterstützung](floating-point-support.md)
## [Eingabe und Ausgabe](input-and-output.md)
### [Text- und Binärmodusdatei-E/A](text-and-binary-mode-file-i-o.md)
### [Unicodestream-E/A im Text- und Binärmodus](unicode-stream-i-o-in-text-and-binary-modes.md)
### [Stream-E/A](stream-i-o.md)
### [E/A auf niedriger Ebene](low-level-i-o.md)
### [Konsole und Port-E/A](console-and-port-i-o.md)
### [_nolock-Funktionen](nolock-functions.md)
## [Internationalisierung](internationalization.md)
### [Locale](locale.md)
### [Codepages](code-pages.md)
### [Interpretation von Multibyte-Zeichensequenzen](interpretation-of-multibyte-character-sequences.md)
### [ISO646-Operatoren](iso646-operators.md)
### [Einzelbyte- und Mehrbyte-Zeichensätze](single-byte-and-multibyte-character-sets.md)
### [SBCS- und MBCS-Datentypen](sbcs-and-mbcs-data-types.md)
### [Unicode: Der Breitzeichensatz](unicode-the-wide-character-set.md)
### [Verwenden von Zuordnungen für generischen Text](using-generic-text-mappings.md)
### [Beispiel für ein Programm mit generischem Text](a-sample-generic-text-program.md)
### [Verwenden von TCHAR.H-Datentypen mit _MBCS](using-tchar-h-data-types-with-mbcs.md)
## [Speicherreservierung](memory-allocation.md)
## [Prozess- und Umgebungssteuerung](process-and-environment-control.md)
## [Stabilität](robustness.md)
## [Laufzeitfehlerüberprüfung](run-time-error-checking.md)
## [Suchen und Sortieren](searching-and-sorting.md)
## [Zeichenfolgenbearbeitung (CRT)](string-manipulation-crt.md)
## [Systemaufrufe](system-calls.md)
## [Uhrzeitverwaltung](time-management.md)
## [CRT-Funktionen, die nicht von Windows-Runtime unterstützt werden](windows-runtime-unsupported-crt-functions.md)
## [Interne globale CRT-Elemente und Funktionen](internal-crt-globals-and-functions.md)
### [_abnormal_termination](abnormal-termination.md)
### [_acmdln, _tcmdln, _wcmdln](acmdln-tcmdln-wcmdln.md)
### [_CIatan](ciatan.md)
### [_CIatan2](ciatan2.md)
### [_CIcos](cicos.md)
### [_CIexp](ciexp.md)
### [_CIfmod](cifmod.md)
### [_CIlog](cilog.md)
### [_CIlog10](cilog10.md)
### [_CIpow](cipow.md)
### [_CIsin](cisin.md)
### [_CIsqrt](cisqrt.md)
### [_CItan](citan.md)
### [__crtLCMapStringW](crtlcmapstringw.md)
### [__CxxFrameHandler](cxxframehandler.md)
### [__dllonexit](dllonexit.md)
### [_except_handler3](except-handler3.md)
### [_execute_onexit_table, _initialize_onexit_table, _register_onexit_function](execute-onexit-table-initialize-onexit-table-register-onexit-function.md)
### [__getmainargs, __wgetmainargs](getmainargs-wgetmainargs.md)
### [___lc_codepage_func](lc-codepage-func.md)
### [___lc_collate_cp_func](lc-collate-cp-func.md)
### [___lc_locale_name_func](lc-locale-name-func.md)
### [_local_unwind2](local-unwind2.md)
### [___mb_cur_max_func, ___mb_cur_max_l_func, __p___mb_cur_max, __mb_cur_max](mb-cur-max-func-mb-cur-max-l-func-p-mb-cur-max-mb-cur-max.md)
### [__p__commode](p-commode.md)
### [__p__fmode](p-fmode.md)
### [__pctype_func](pctype-func.md)
### [__RTDynamicCast](rtdynamiccast.md)
### [__set_app_type](internal-set-app-type.md)
### [_set_app_type](set-app-type.md)
### [_setjmp3](setjmp3.md)
### [___setlc_active_func, ___unguarded_readlc_active_add_func](setlc-active-func-unguarded-readlc-active-add-func.md)
### [__setusermatherr](setusermatherr.md)
# [Globale Variablen und Standardtypen](global-variables-and-standard-types.md)
## [Globale Variablen](global-variables.md)
### [__argc, __argv, __wargv](argc-argv-wargv.md)
### [_daylight, _dstbias, _timezone, and _tzname](daylight-dstbias-timezone-and-tzname.md)
### [errno, _doserrno, _sys_errlist, and _sys_nerr](errno-doserrno-sys-errlist-and-sys-nerr.md)
### [_environ, _wenviron](environ-wenviron.md)
### [_fmode](fmode.md)
### [_iob](iob.md)
### [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](pctype-pwctype-wctype-mbctype-mbcasemap.md)
### [_pgmptr, _wpgmptr](pgmptr-wpgmptr.md)
## [Control Flags](control-flags.md)
### [_CRTDBG_MAP_ALLOC](crtdbg-map-alloc.md)
### [_DEBUG](debug.md)
### [_crtDbgFlag](crtdbgflag.md)
## [Standardtypen](standard-types.md)
# [Globale Konstanten](global-constants.md)
## [32-Bit-Windows-Uhrzeit-/Datumsformate](32-bit-windows-time-date-formats.md)
## [BUFSIZ](bufsiz.md)
## [CLOCKS_PER_SEC, CLK_TCK](clocks-per-sec-clk-tck.md)
## [Commit-To-Disk-Konstanten](commit-to-disk-constants.md)
## [_CRT_DISABLE_PERFCRIT_LOCKS](crt-disable-perfcrit-locks.md)
## [Datentypkonstanten](data-type-constants.md)
## [Umgebungskonstanten](environmental-constants.md)
## [EOF, WEOF](eof-weof.md)
## [errno-Konstanten](errno-constants.md)
## [Ausnahmebehandlungskonstanten](exception-handling-constants.md)
## [EXIT_SUCCESS, EXIT_FAILURE](exit-success-exit-failure.md)
## [Dateiattributskonstanten](file-attribute-constants.md)
## [Dateikonstanten](file-constants.md)
## [Dateiberechtigungskonstanten](file-permission-constants.md)
## [Datei-Lese-/Schreibzugriffkonstanten](file-read-write-access-constants.md)
## [Dateiübersetzungskonstanten](file-translation-constants.md)
## [FILENAME_MAX](filename-max.md)
## [FOPEN_MAX, _SYS_OPEN](fopen-max-sys-open.md)
## [_FREEENTRY, _USEDENTRY](freeentry-usedentry.md)
## [fseek- und _lseek-Konstanten](fseek-lseek-constants.md)
## [heap-Konstanten](heap-constants.md)
## [_HEAP_MAXREQ](heap-maxreq.md)
## [HUGE_VAL, _HUGE](huge-val-huge.md)
## [Gebietsschemakategorien](locale-categories.md)
## [_locking-Konstanten](locking-constants.md)
## [Math-Konstanten](math-constants.md)
## [Mathematische Fehlerkonstanten](math-error-constants.md)
## [_MAX_ENV](max-env.md)
## [MB_CUR_MAX](mb-cur-max.md)
## [NULL (CRT)](null-crt.md)
## [Begrenzungen für Pfadfelder](path-field-limits.md)
## [RAND_MAX](rand-max.md)
## [setvbuf-Konstanten](setvbuf-constants.md)
## [Freigeben von Konstanten](sharing-constants.md)
## [Signalkonstanten](signal-constants.md)
## [Signalaktionskonstante](signal-action-constants.md)
## [spawn-Konstanten](spawn-constants.md)
## [_stat Structure st_mode-Feldkonstanten](stat-structure-st-mode-field-constants.md)
## [stdin, stdout, stderr](stdin-stdout-stderr.md)
## [TMP_MAX, L_tmpnam](tmp-max-l-tmpnam.md)
## [Übersetzungsmoduskonstanten](translation-mode-constants.md)
## [_TRUNCATE](truncate.md)
## [TZNAME_MAX](tzname-max.md)
## [_WAIT_CHILD, _WAIT_GRANDCHILD](wait-child-wait-grandchild.md)
## [WCHAR_MAX](wchar-max.md)
## [WCHAR_MIN](wchar-min.md)
# [Allgemeintext-Zuordnungen](generic-text-mappings.md)
## [Datentypzuordnungen](data-type-mappings.md)
## [Zuordnungen von Konstanten und globalen Variablen](constant-and-global-variable-mappings.md)
## [Routinezuordnungen](routine-mappings.md)
# [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](locale-names-languages-and-country-region-strings.md)
## [Language Strings](language-strings.md)
## [Country/Region Strings](country-region-strings.md)
# [Übersichten über die Funktionsfamilie](function-family-overviews.md)
## [_exec- und _wexec-Funktionen](exec-wexec-functions.md)
## [Dateinamen-Suchfunktionen](filename-search-functions.md)
## [Syntax der Formatangabe: printf- und wprintf-Funktionen](format-specification-syntax-printf-and-wprintf-functions.md)
## [Formatangabefelder: scanf- und wscanf-Funktionen](format-specification-fields-scanf-and-wscanf-functions.md)
## [is- und isw-Routinen](is-isw-routines.md)
## [_ismbb-Routinen](ismbb-routines.md)
## [ismbc-Routinen](ismbc-routines.md)
## [operator new(CRT)](new-operator-crt.md)
## [operator new (CRT)](operator-new-crt.md)
## [operator delete(CRT)](delete-operator-crt.md)
## [operator delete (CRT)](operator-delete-crt.md)
## [printf_p-Positionsparameter](printf-p-positional-parameters.md)
## [scanf-Typenfeldzeichen](scanf-type-field-characters.md)
## [scanf-Breitenangabe](scanf-width-specification.md)
## [_spawn-, _wspawn-Funktionen](spawn-wspawn-functions.md)
## [strcoll-Funktionen](strcoll-functions.md)
## [Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](string-to-numeric-value-functions.md)
## [to-Funktionen](to-functions.md)
## [vprintf-Funktionen](vprintf-functions.md)
# [Veraltete Funktionen](obsolete-functions.md)
## [_cgets, _cgetws](cgets-cgetws.md)
## [_get_output_format](get-output-format.md)
## [gets, _getws](gets-getws.md)
## [_heapadd](heapadd.md)
## [_heapset](heapset.md)
## [inp, inpw](inp-inpw.md)
## [_inp, _inpw, _inpd](inp-inpw-inpd.md)
## [_lock](lock.md)
## [outp, outpw](outp-outpw.md)
## [_outp, _outpw, _outpd](outp-outpw-outpd.md)
## [_set_output_format](set-output-format.md)
## [_unlock](unlock.md)
# [Alphabetische Funktionsreferenz](reference/TOC.md)