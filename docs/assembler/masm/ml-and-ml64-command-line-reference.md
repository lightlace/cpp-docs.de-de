---
title: ML- und ML64-Befehlszeilenreferenz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ML
dev_langs:
- C++
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41d3603bc09b7c63fdd152e1c7d5921c2bb3eb7c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693402"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML- und ML64-Befehlszeilenreferenz

Assembliert und Quelldateien für eine oder mehrere Assemblysprache verknüpft wird. Die Befehlszeilenoptionen werden Groß-/Kleinschreibung beachtet.

Weitere Informationen zu ml64.exe, finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="syntax"></a>Syntax

> ML [[*Optionen*]] *Filename* [[[[*Optionen*]] *Filename*]]

> ML64 [[*Optionen*]] *Filename* [[[[*Optionen*]] *Filename*]]... [[/ link *Linkoptions*]]

### <a name="parameters"></a>Parameter

*Optionen*<br/>
In der folgenden Tabelle aufgeführten Optionen.

|Option|Aktion|
|------------|------------|
|**/AT**|Ermöglicht die Unterstützung von kleinen-Memory-Modell. Fehlermeldungen für Konstrukte auf Codeebene, die die Anforderungen für die COM-Format-Dateien zu verletzen aktiviert. Beachten Sie, dass dies nicht, für entspricht die [. Modell](../../assembler/masm/dot-model.md) **WINZIG** Richtlinie.<br /><br /> In ml64.exe nicht verfügbar.|
|**/ Bl** *Dateiname*|Wählt eine alternative Linker.|
|**/c**|Nur assembliert. Ist nicht verknüpft werden.|
|**/coff**|Allgemeine Datei-Format (COFF) Objekttyp des Objektmodul wird generiert. Im Allgemeinen erforderlich, für die Entwicklung von Win32-Assemblysprache.<br /><br /> In ml64.exe nicht verfügbar.|
|**/Cp**|Groß-/Kleinschreibung, der alle Benutzer-IDs werden beibehalten.|
|**/ Cu**|Ordnet alle Bezeichner in Großbuchstaben (Standard).<br /><br /> In ml64.exe nicht verfügbar.|
|**/Cx**|Behält Groß-/Kleinschreibung im öffentlichen und Extern-Symbole.|
|**/ D** *Symbol*[[=*Wert*]]|Definiert ein Textmakro, mit dem angegebenen Namen. Wenn *Wert* ist nicht vorhanden ist, ist es leer. Mehrere durch Leerzeichen getrennte Token müssen in Anführungszeichen eingeschlossen werden.|
|**/ EP**|Generiert eine vorverarbeitete quellcodeauflistung (an "stdout" gesendet). Finden Sie unter **/SF**.|
|**/ ERRORREPORT** [ **NONE** &AMP;#124; **EINGABEAUFFORDERUNG** &AMP;#124; **WARTESCHLANGE** &AMP;#124; **SENDEN** ]|Wenn ml.exe "oder" ml64.exe zur Laufzeit fehlschlägt, können Sie **/errorreport** Informationen zu diesen internen Fehlern an Microsoft zu senden.<br /><br /> Weitere Informationen zu **/errorreport**, finden Sie unter [/errorreport (interne Compilerfehler Bericht)](../../build/reference/errorreport-report-internal-compiler-errors.md).|
|**/ F** *Hexnum*|Legt die Stapelgröße auf *Hexnum* Bytes (Dies entspricht dem **/Link/STACK**:*Anzahl*). Der Wert muss in hexadezimaler Schreibweise ausgedrückt werden. Es muss ein Leerzeichen zwischen **/f** und *Hexnum*.|
|**/ FE** *Dateiname*|Benennt die ausführbare Datei an.|
|**/ Fl**[[*Filename*]]|Generiert eine assemblierte Codeliste an. Finden Sie unter **/SF**.|
|**/ FM**[[*Filename*]]|Erstellt eine Zuordnungsdatei für den Linker an.|
|**/ Fo** *Dateiname*|Benennt eine Objektdatei. Weitere Informationen finden Sie unter "Hinweise" Abschnitt.|
|**/FPi**|Generiert die Emulator-Korrekturen Gleitkommazahlen (nur gemischter Language).<br /><br /> In ml64.exe nicht verfügbar.|
|**/ FR**[[*Filename*]]|Generiert eine Quelle Browser SBR-Datei.|
|**/ FR**[[*Filename*]]|Generiert eine erweiterte Form einer Quelle Browser SBR-Datei an.|
|**/Gc**|Gibt an, FORTRAN - Pascal-Schreibweise Format-Funktion aufrufen und Benennungskonventionen. Identisch mit **OPTION Sprache: PASCAL**.<br /><br /> In ml64.exe nicht verfügbar.|
|**/Gd**|Gibt an, der C-Format-Funktion aufrufen und Benennungskonventionen. Identisch mit **OPTION Sprache: C**.<br /><br /> In ml64.exe nicht verfügbar.|
|**/GZ**|Gibt an, der __stdcall-Funktion aufrufen und Benennungskonventionen.  Identisch mit **OPTION Sprache: STCALL**.<br /><br /> In ml64.exe nicht verfügbar.|
|**/ H** *Anzahl*|Beschränkt den externe Namen auf der Anzahl von signifikanten Zeichen. Der Standardwert ist 31 Zeichen.<br /><br /> In ml64.exe nicht verfügbar.|
|**/help**|Hilfe zu ML erfordert QuickHelp.|
|**/ I** *Pfadname*|Legt den Pfad für Include-Datei. Maximal 10 **/i** -Optionen zulässig ist.|
|**/nologo**|Unterdrückt die Nachrichten für die erfolgreiche Assembly.|
|**/omf**|Objekt-Modul (OMF)-Dateiformattyp des Objektmoduls wird generiert.  **"/ OMF"** impliziert **/c**; ML.exe wird das Verknüpfen von OMF-Objekte nicht unterstützt.<br /><br /> In ml64.exe nicht verfügbar.|
|**/Sa**|Aktiviert die Liste aller verfügbaren Informationen.|
|**/safeseh**|Markiert das Objekt als entweder, enthält keine Ausnahmehandler oder einer darin enthaltenen ausnahmehandlern, die alle mit deklariert werden [. SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> In ml64.exe nicht verfügbar.|
|**/Sf**|Fügt die First-Pass-Angebot zu Listendatei.|
|**/ SL** *Breite*|Legt die Linienstärke der Quelle, die Auflistung in Zeichen pro Zeile fest. Bereich ist 0 oder 60 bis 255. Standardwert ist 0. Identisch mit [Seite](../../assembler/masm/page.md) Breite.|
|**/Sn**|Deaktiviert die Symboltabelle, beim Erstellen einer Auflistung.|
|**/ SP** *Länge*|Legt die Seitenlänge der Auflistung in Zeilen pro Seite Quelle fest. Bereich ist 0 oder 10 bis 255. Standardwert ist 0. Identisch mit [Seite](../../assembler/masm/page.md) Länge.|
|**/ Ss** *Text*|Gibt den Text für quellcodeauflistung. Identisch mit [UNTERTITEL](../../assembler/masm/subtitle.md) Text.|
|**/ St** *Text*|Gibt die Titel für quellcodeauflistung an. Identisch mit [Titel](../../assembler/masm/title.md) Text.|
|**/Sx**|Aktiviert auf "false" Bedingungen in der Auflistung.|
|**/ TA** *Dateiname*|Assembliert die Quelldatei, dessen Name nicht mit der ASM-Erweiterung endet.|
|**/w**|Identisch mit **/W0/WX**.|
|**/ W** *Ebene*|Legt die Warnstufe fest, in denen *Ebene* = 0, 1, 2 oder 3.|
|**/WX**|Gibt einen Fehlercode zurück, wenn Warnungen generiert werden.|
|**/X**|Ignorieren Sie Includepfad-Umgebung.|
|**/Zd**|Generiert Zeilennummerninformationen in Objektdatei.|
|**/Zf**|Macht alle Symbole öffentlichen.|
|**/Zi**|Generiert CodeView-Informationen in der Objektdatei.|
|**/Zm**|Ermöglicht**M510** Option für maximale Kompatibilität mit MASM 5.1.<br /><br /> In ml64.exe nicht verfügbar.|
|**/ Zp**[[*Ausrichtung*]]|Komprimiert Strukturen auf die angegebene Byte-Grenze. Die *Ausrichtung* kann 1, 2 oder 4 sein.|
|**/Zs**|Führt nur eine syntaxüberprüfung an.|
|**/?**|Zeigt eine Zusammenfassung der Befehlszeilensyntax ML.|

*filename*<br/>
Der Name der Datei.

*linkoptions*<br/>
Die Linkoptionen.  Finden Sie unter [Optionen des Linkers](../../build/reference/linker-options.md) für Weitere Informationen.

## <a name="remarks"></a>Hinweise

Einige Befehlszeilenoptionen ml- und ML64 sind Platzierung Akzent. Z. B. weil ml- und ML64 mehrere akzeptieren kann **/c** Optionen, die alle entsprechenden **/Fo** Optionen müssen angegeben werden, bevor Sie **/c**. Das folgende Befehlszeilenbeispiel veranschaulicht eine Objekt-Dateispezifikation für die einzelnen Spezifikation für die testassemblydatei:

**ml.exe/Fo a1.obj/c a.asm/Fo b1.obj b.asm/c**

## <a name="environment-variables"></a>Umgebungsvariablen

|Variable|Beschreibung|
|--------------|-----------------|
|INCLUDE|Gibt die Suchpfad für die Includedateien an.|
|ML|Gibt die Standard-Befehlszeilenoptionen an.|
|TMP|Gibt Pfad für temporäre Dateien.|

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>
[Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>