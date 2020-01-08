---
title: ML- und ML64-Befehlszeilenreferenz
ms.date: 12/17/2019
f1_keywords:
- ML
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
ms.openlocfilehash: 77385317ab7f90a646b7f552e471d0f434e72bfb
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317161"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML- und ML64-Befehlszeilenreferenz

Assembliert und verknüpft eine oder mehrere Assemblysprachen-Quelldateien. Bei den Befehlszeilenoptionen wird die Groß-/Kleinschreibung beachtet.

Weitere Informationen zu ml64. exe finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="syntax"></a>Syntax

> ML-\[*Optionen*] *Dateiname* \[ \[*Optionen*] *Dateiname*]
>
> Ml64 \[*options*] *Dateiname* \[ \[*Optionen*] *Dateiname*]... \[/Link *linkoptions*]

### <a name="parameters"></a>Parameters

*Optionen*\
Die in der folgenden Tabelle aufgeführten Optionen.

|-Option|-Aktion|
|------------|------------|
|**/AT**|Ermöglicht die Unterstützung von kleinen Arbeitsspeicher Modellen. Aktiviert Fehlermeldungen für Codekonstrukte, die die Anforderungen für com-Format Dateien verletzen. Beachten Sie, dass dies nicht dem entspricht [. ](dot-model.md) **Kleine** Modell Direktive.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/BL** *Dateiname*|Wählt einen alternativen Linker aus.|
|**/c**|Nur assembliert. Nicht verknüpft.|
|**/coff**|Generiert Common Object File Format (COFF)-Typ des Objekt Moduls. Für die Entwicklung von Win32-Assemblys erforderlich.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Cp**|Speichert die Groß-/Kleinschreibung aller Benutzer Bezeichner.|
|**/Cu**|Ordnet alle Bezeichner Großbuchstaben zu (Standard).<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Cx**|Speichert groß-und Kleinbuchstaben in öffentlichen und externen Symbolen.|
|**/D** *Symbol*⟦ =*Wert*⟧|Definiert ein Text Makro mit dem angegebenen Namen. Wenn der *Wert* fehlt, ist er leer. Mehrere durch Leerzeichen getrennte Token müssen in Anführungszeichen eingeschlossen werden.|
|**/EP**|Generiert eine vorverarbeitete Quell Auflistung (die an stdout gesendet wird). Siehe **/SF**.|
|**/errorreport** [ **keine** &#124; **prompt** &#124; - **Warteschlange** &#124; **senden** ]|Wenn ml. exe oder ml64. exe zur Laufzeit fehlschlägt, können Sie **/errorreport** verwenden, um Informationen zu diesen internen Fehlern an Microsoft zu senden.<br /><br /> Weitere Informationen zu **/errorreport**finden Sie unter [/errorreport (interne Compilerfehler melden)](../../build/reference/errorreport-report-internal-compiler-errors.md).|
|**/F** *Hexnum*|Legt die Stapelgröße auf *Hexnum* Bytes fest (entspricht dem Wert von **/Link/Stack**:*Number*). Der Wert muss in hexadezimal Notation ausgedrückt werden. Zwischen **/F** und *Hexnum*muss ein Leerzeichen stehen.|
|**/FE** *Dateiname*|Benennt die ausführbare Datei.|
|**/FL**⟦*Dateiname*⟧|Generiert eine assemblierte Codeliste. Siehe **/SF**.|
|**/FM**⟦*Dateiname*⟧|Erstellt eine Linker-Zuordnungs Datei.|
|**/FO** *Dateiname*|Benennt eine Objektdatei. Weitere Informationen finden Sie im Abschnitt "Hinweise".|
|**/FPi**|Generiert Emulator-Fixups für Gleit Komma Arithmetik (nur gemischte Sprache).<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Fr**⟦*Dateiname*⟧|Generiert eine SBR-Datei des Quell Browsers.|
|**/Fr**⟦*Dateiname*⟧|Generiert eine erweiterte Form der SBR-Datei des Quell Browsers.|
|**/Gc**|Gibt die Verwendung von Fortran-oder Pascal-Funktionsaufrufen und Namenskonventionen an. Identisch mit **options Sprache: Pascal**.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Gd**|Gibt die Verwendung von Funktionsaufrufen und Namenskonventionen im C-Stil an. Identisch mit der **options Sprache: C**.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/GZ**|Gibt die Verwendung von __stdcall Funktionsaufrufen und Namenskonventionen an.  Identisch mit **options Sprache: stcallcenter**.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/H** - *Nummer*|Schränkt externe Namen auf eine Zahl signifikanter Zeichen ein. Der Standardwert ist 31 Zeichen.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/help**|Ruft QuickHelp für Hilfe zu ml auf.|
|**/I** *Pfadname*|Legt den Pfad für die Includedatei fest. Maximal 10 **/I** Optionen sind zulässig.|
|**/nologo**|Unterdrückt Meldungen für die erfolgreiche Assembly.|
|**/omf**|Generiert den OMF-Typ (Object Module File Format) des Objekt Moduls.  **/OMF** impliziert **/c**; "Ml. exe" unterstützt nicht das Verknüpfen von OMF-Objekten.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Sa**|Schaltet die Auflistung aller verfügbaren Informationen ein.|
|**/safeseh**|Markiert das-Objekt als, das entweder keine Ausnahmehandler enthält oder Ausnahmehandler enthält, die alle mit deklariert sind [. SAFESEH](dot-safeseh.md).<br /><br /> Nicht verfügbar in ml64. exe.|
|**/Sf**|Fügt eine erste-Pass-Auflistung zur Listen Datei hinzu.|
|**/SL** - *Breite*|Legt die Linienbreite des Quell Auflistungen in Zeichen pro Zeile fest. Der Bereich liegt zwischen 60 und 255 oder 0. Standard ist "0". Identisch mit der [Seiten](page.md) Breite.|
|**/Sn**|Deaktiviert die Symboltabelle, wenn eine Auflistung erzeugt wird.|
|**/SP** - *Länge*|Legt die Seitenlänge des Quell Auflistungen in Zeilen pro Seite fest. Der Bereich liegt zwischen 10 und 255 oder 0. Standard ist "0". Identisch mit der [Seiten](page.md) Länge.|
|**/SS** *Text*|Gibt Text für die Quell Auflistung an. Identisch mit unter [Titel](subtitle.md) Text.|
|**/St** *Text*|Gibt den Titel für die Quell Auflistung an. Identisch mit [Titeltext](title.md) .|
|**/Sx**|Schaltet falsche Bedingungen in der Auflistung ein.|
|**/Ta** *Dateiname*|Assembliert die Quelldatei, deren Name nicht mit der ASM-Erweiterung endet.|
|**/w**|Identisch mit **/W0/WX**.|
|**/W** - *Ebene*|Legt die Warnstufe fest, wobei *Level* = 0, 1, 2 oder 3 ist.|
|**/WX**|Gibt einen Fehlercode zurück, wenn Warnungen generiert werden.|
|**/X**|INCLUDE-Umgebungs Pfad ignorieren.|
|**/Zd**|Generiert Zeilennummern Informationen in der Objektdatei.|
|**/Zf**|Macht alle Symbole als öffentlich.|
|**/Zi**|Generiert CodeView-Informationen in der Objektdatei.|
|**/Zm**|Aktiviert die**M510** -Option für maximale Kompatibilität mit MASM 5,1.<br /><br /> Nicht verfügbar in ml64. exe.|
|**/ZP**⟦*Alignment*⟧|Packt Strukturen an der angegebenen Byte Grenze. Die *Ausrichtung* kann 1, 2 oder 4 sein.|
|**/Zs**|Führt nur eine Syntax Überprüfung aus.|
|**/?**|Zeigt eine Zusammenfassung der ml-Befehlszeilen Syntax an.|

*Dateiname*\
Der Name der Datei.

*linkoptions* -\
Die Link Optionen.  Weitere Informationen finden Sie unter [Linkeroptionen](../../build/reference/linker-options.md) .

## <a name="remarks"></a>Hinweise

Einige Befehlszeilenoptionen für ml und ML64 sind Platzierungs abhängig. Da z. b. ml und ML64 mehrere **/c** -Optionen akzeptieren können, müssen vor **/c**alle entsprechenden **/FO** -Optionen angegeben werden. Im folgenden Befehlszeilen Beispiel wird eine Objektdatei Spezifikation für jede assemblydateispezifikation veranschaulicht:

**ml. exe/FO a1. obj/c a. ASM/FO B1. obj/c b. asm**

## <a name="environment-variables"></a>Umgebungsvariablen

|Variable|Beschreibung|
|--------------|-----------------|
|INCLUDE|Gibt den Suchpfad für Includedateien an.|
|ML|Gibt standardmäßige Befehlszeilenoptionen an.|
|TMP|Gibt den Pfad für temporäre Dateien an.|

## <a name="see-also"></a>Siehe auch

[Ml-Fehlermeldungen](ml-error-messages.md)\
[Referenz zum Microsoft-Makroassembler](microsoft-macro-assembler-reference.md)
