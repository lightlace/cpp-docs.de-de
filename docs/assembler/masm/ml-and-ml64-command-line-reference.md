---
title: ML- und ML64-Befehlszeilenreferenz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: da3fb143aeaaf6fa8cf31c45b31707fa01bf6898
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="ml-and-ml64-command-line-reference"></a>ML- und ML64-Befehlszeilenreferenz
Assembliert und Quelldateien für eine oder mehrere Assemblersprache verknüpft. Die Befehlszeilenoptionen werden Groß-/Kleinschreibung beachtet.  
  
 Weitere Informationen zu ml64.exe, finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### <a name="parameters"></a>Parameter  
 `options`  
 In der folgenden Tabelle aufgeführten Optionen.  
  
|Option|Aktion|  
|------------|------------|  
|**/AT**|Ermöglicht die Unterstützung von kleinen Speichermodell. Ermöglicht die Fehlermeldungen für Codekonstrukte, die die Anforderungen für Dateien im Format ".com" verletzen. Beachten Sie, dass dies nicht entspricht der [. Modell](../../assembler/masm/dot-model.md) **sehr klein** Richtlinie.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Bl** `filename`|Wählt eine alternative Linker.|  
|**/c**|Nur assembliert. Enthält keine Links.|  
|**/coff**|Allgemeine Datei-Format (COFF) Objekttyp des Objektmodul wird generiert. Im Allgemeinen erforderlich für die Win32-Assemblysprache Entwicklung.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Cp**|Behält Groß-/Kleinschreibung aller Benutzer-IDs an.|  
|**/ Cu**|Ordnet alle Bezeichner in Großbuchstaben (Standard).<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Cx**|Groß-/Kleinschreibung, in öffentlichen und "extern" Symbole beibehalten.|  
|**/D** `symbol`[[=`value`]]|Definiert ein Textmakro mit dem angegebenen Namen. Wenn `value` ist nicht vorhanden ist, ist es leer. Mehrere durch Leerzeichen getrennte Token müssen in Anführungszeichen eingeschlossen werden.|  
|**/ EP**|Generiert eine vorverarbeitete Quelle auflisten (gesendet an "stdout"). Finden Sie unter **/SF**.|  
|**/ ERRORREPORT** [ **NONE** &AMP;#124; **PROMPT** &AMP;#124; **WARTESCHLANGE** &AMP;#124; **SENDEN** ]|Wenn ml.exe oder ml64.exe zur Laufzeit fehlschlägt, können Sie **/errorreport** Informationen zu diesen internen Fehlern an Microsoft zu senden.<br /><br /> Weitere Informationen zu **/errorreport**, finden Sie unter [/errorreport (Bericht interne Compilerfehler)](../../build/reference/errorreport-report-internal-compiler-errors.md).|  
|**/F** `hexnum`|Legt die Stapelgröße zum `hexnum` Bytes (Dies ist identisch mit **/Link/Stapel**:`number`). Der Wert muss in hexadezimaler Schreibweise ausgedrückt werden. Es muss ein Leerzeichen zwischen **/f** und `hexnum`.|  
|**/Fe** `filename`|Benennt die ausführbare Datei an.|  
|**/Fl**[[`filename`]]|Generiert eine assemblierte Codeliste. Finden Sie unter **/SF**.|  
|**/Fm**[[`filename`]]|Erstellt eine Zuordnungsdatei Linker.|  
|**/Fo** `filename`|Benennt eine Objektdatei. Weitere Informationen finden Sie unter "Hinweise" Abschnitt.|  
|**/FPi**|Generiert Emulator Reparaturen für Gleitkommazahlen (nur gemischter Language) an.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Fr**[[`filename`]]|Generiert eine Quelle Browser SBR-Datei.|  
|**/FR**[[`filename`]]|Generiert eine erweiterte Form einer Quelle Browser SBR-Datei an.|  
|**/Gc**|Gibt an, dass der FORTRAN-Pascal-Format-Funktion aufrufen und Benennungskonventionen. Identisch mit **OPTION LANGUAGE: PASCAL**.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Gd**|Gibt an, dass der C-Format-Funktion aufrufen und Benennungskonventionen. Identisch mit **OPTION LANGUAGE: C**.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/GZ**|Gibt an, dass der __stdcall-Funktion aufrufen und Benennungskonventionen.  Identisch mit **OPTION LANGUAGE: STCALL**.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/H** `number`|Beschränkt den externen Namen auf signifikante Ziffern. Der Standardwert ist 31 Zeichen.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/help**|Hilfe zur ML erfordert Schnellhilfe.|  
|**/I** `pathname`|Legt den Pfad für die Includedatei. Maximal 10 **/i** Optionen ist zulässig.|  
|**/nologo**|Unterdrückt die Nachrichten für erfolgreiche Assembly.|  
|**/omf**|Datei-Format (OMF)-Typen für die Objekt-Modul von Objektmodul erzeugt.  **/ OMF** impliziert **/c**; ML.exe unterstützt Verknüpfen von OMF-Objekte nicht.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Sa**|Aktiviert die Liste aller verfügbaren Informationen.|  
|**/safeseh**|Markiert das Objekt als "" enthält keine Ausnahmehandler oder enthält Ausnahmehandler, die alle mit deklariert werden [. SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Sf**|Fügt ersten Durchlauf Angebot zu Listendatei.|  
|**/Sl** `width`|Legt die Linienstärke des Quelle auflisten von Zeichen pro Zeile an. Bereich ist 60 bis 255 oder 0. Standard ist 0. Identisch mit [Seite](../../assembler/masm/page.md) Breite.|  
|**/Sn**|Deaktiviert die Symboltabelle bei, der eine Liste erzeugt.|  
|**/Sp** `length`|Legt die Seitenlänge der Quelle auflisten der Zeilen pro Seite fest. Bereich ist 10 bis 255 oder 0. Standard ist 0. Identisch mit [Seite](../../assembler/masm/page.md) Länge.|  
|**/Ss** `text`|Gibt den Text für die Quelle auflisten. Identisch mit [UNTERTITEL](../../assembler/masm/subtitle.md) Text.|  
|**/St** `text`|Gibt die Titel für die Quelle auflisten. Identisch mit [Titel](../../assembler/masm/title.md) Text.|  
|**/Sx**|Aktiviert die "false" Konditionelle Abschnitte in der Auflistung.|  
|**/Ta** `filename`|Assembliert die Quelldatei, deren Name nicht mit der ASM-Erweiterung endet.|  
|**/w**|Identisch mit **/W0/WX**.|  
|**/W** `level`|Legt die Warnstufe fest, in denen `level` = 0, 1, 2 oder 3.|  
|**/WX**|Wird ein Fehlercode zurückgegeben, wenn Warnungen generiert werden.|  
|**/X**|Ignorieren Sie die Umgebung der INCLUDE-Pfad.|  
|**/Zd**|Nummer der Zeile Informationen werden in der Objektdatei generiert.|  
|**/Zf**|Macht alle Symbole öffentlichen.|  
|**/Zi**|Generiert Codeansichtsinformationen in der Objektdatei.|  
|**/Zm**|Ermöglicht**M510** Option für die maximale Kompatibilität mit MASM 5.1.<br /><br /> In ml64.exe nicht verfügbar.|  
|**/Zp**[[`alignment`]]|Packs Strukturen für die angegebene Byte-Grenze. Die `alignment` kann 1, 2 oder 4 sein.|  
|**/Zs**|Führt nur eine syntaxüberprüfung.|  
|**/?**|Zeigt eine Zusammenfassung der Befehlszeilensyntax ML.|  
  
 `filename`  
 Der Name der Datei.  
  
 `linkoptions`  
 Die Linkoptionen.  Finden Sie unter [Optionen des Linkers](../../build/reference/linker-options.md) für Weitere Informationen.  
  
## <a name="remarks"></a>Hinweise  
 Einige Befehlszeilenoptionen ml- und ML64 Groß-/Kleinschreibung beachtet Platzierung. Z. B. weil ml- und ML64 mehrere akzeptieren kann **/c** Optionen, die alle entsprechenden **/Fo** Optionen müssen angegeben werden, bevor Sie **/c**. Das folgende Befehlszeilenbeispiel wird ein Objekt Dateispezifikation für jede Assembly Dateispezifikation veranschaulicht:  
  
 **ml.exe/Fo a1.obj/c a.asm/Fo b1.obj/c b.asm**  
  
## <a name="environment-variables"></a>Umgebungsvariablen  
  
|Variable|Beschreibung|  
|--------------|-----------------|  
|INCLUDE|Gibt Suchpfad nach Includedateien an.|  
|ML|Gibt Befehlszeilenoptionen an Standardeinstellung.|  
|TMP|Gibt an, der Pfad für temporäre Dateien.|  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)   
 [Referenz zum Microsoft-Makroassembler](../../assembler/masm/microsoft-macro-assembler-reference.md)