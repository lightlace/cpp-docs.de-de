---
title: "ML and ML64 Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ML"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/W* MASM compiler option"
  - "/c MASM compiler option"
  - "/EP MASM compiler option"
  - "/Fe MASM compiler option"
  - "/Zp MASM compiler option"
  - "/AT MASM compiler option"
  - "/Zm MASM compiler option"
  - "/Sf MASM compiler option"
  - "/Sp MASM compiler option"
  - "/w MASM compiler option"
  - "/Fl MASM compiler option"
  - "/coff MASM compiler option"
  - "/St MASM compiler option"
  - "/Cx MASM compiler option"
  - "/Sl MASM compiler option"
  - "/Cu MASM compiler option"
  - "MASM (Microsoft Macro Assembler), ML command-line reference"
  - "/FPi MASM compiler option"
  - "/Zf MASM compiler option"
  - "ML environment variable"
  - "/Fr MASM compiler option"
  - "/help MASM compiler option"
  - "/Sa MASM compiler option"
  - "/Zd MASM compiler option"
  - "/I MASM compiler option"
  - "/? MASM compiler option"
  - "/Bl MASM compiler option"
  - "/Fm MASM compiler option"
  - "/Fo MASM compiler option"
  - "command-line reference [ML]"
  - "/Sn MASM compiler option"
  - "/Gd MASM compiler option"
  - "/D* MASM compiler option"
  - "environment variables, ML"
  - "/Gc MASM compiler option"
  - "/F* MASM compiler option"
  - "/Sc MASM compiler option"
  - "/H MASM compiler option"
  - "/Zs MASM compiler option"
  - "/omf MASM compiler option"
  - "/Sg MASM compiler option"
  - "/Cp MASM compiler option"
  - "/Zi MASM compiler option"
  - "/nologo MASM compiler option"
  - "/Sx MASM compiler option"
  - "/WX MASM compiler option"
  - "/Ss MASM compiler option"
  - "command line, reference [ML]"
  - "/Ta MASM compiler option"
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ML and ML64 Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rekonstruiert ein oder mehrere Joins und zusammen Assemblersprachen quelldateien.  Die Befehlszeilenoptionen wird die Groß\-\/Kleinschreibung beachtet.  
  
 Weitere Informationen über ml64.exe finden Sie unter [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Syntax  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### Parameter  
 `options`  
 Die in der folgenden Tabelle aufgeführten Optionen.  
  
|Option|Aktion|  
|------------|------------|  
|**\/AT**|Aktiviert Sehr klein\-ArbeitsspeicherMODEL\-Unterstützung.  Hiermit können Fehlermeldungen für Codekonstrukte, die die Anforderungen für Dateien Format .com\- verletzen.  Beachten Sie, dass dadurch nicht an die Direktive [.MODEL](../../assembler/masm/dot-model.md) **TINY** entspricht.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Bl** `filename`|Wählt einen alternativen Linker aus.|  
|**\/c**|Nur Assembliert.  Verknüpft nicht.|  
|**\/coff**|Generiert Typ im COFF\-Format \(Common Object File Format\) des Objektmoduls.  Im Allgemeinen erforderlich für die Entwicklung Win32\-Assemblersprachen.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Cp**|Behält Groß\-\/Kleinschreibung aller Benutzer\-ID.|  
|**\/Cu**|Ordnet alle Bezeichner in Großbuchstaben \(Standard\).<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Cx**|Behält Fall öffentlich und extern\-Symbole bei.|  
|**\/D** `symbol`\[\[\=`value`\]\]|Definiert ein Text Makro mit dem angegebenen Namen.  Wenn `value` fehlt, ist jedoch leer.  Es wurden mehrere Token, die durch Leerzeichen getrennt sind, müssen in Anführungszeichen eingeschlossen werden.|  
|**\/EP**|Generiert vorverarbeiteten Listen \(Quelle\) STDOUT gesendet.  Weitere Informationen finden Sie unter **\/Sf**.|  
|**\/ERRORREPORT** \[ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** \]|Wenn ml.exe oder ml64.exe zur Laufzeit fehlschlägt, können Sie **\/ERRORREPORT** verwenden, um Informationen über diese internen Fehler an Microsoft zu senden.<br /><br /> Weitere Informationen zu **\/ERRORREPORT** finden Sie unter [\/errorReport \(Meldung über interne Compilerfehler\)](../../build/reference/errorreport-report-internal-compiler-errors.md).|  
|**\/F** `hexnum`|Legt die Stapelgröße in Bytes fest `hexnum` \(dies entspricht **\/link\/STACK**:`number`\).  Der Wert muss in der Hexadezimalnotation ausgedrückt werden.  Es muss ein Leerzeichen zwischen **\/F** und geben `hexnum`.|  
|**\/Fe** `filename`|Namen der ausführbaren Datei.|  
|**\/Fl**\[\[`filename`\]\]|Generiert assemblierten Codeauflistung.  Weitere Informationen finden Sie unter **\/Sf**.|  
|**\/Fm**\[\[`filename`\]\]|Erstellt eine Linker Datei zugeordnet.|  
|**\/Fo** `filename`|Namen einer Objektdatei.  Weitere Informationen finden Sie in Abschnitt " Hinweise ".|  
|**\/FPi**|Generiert Emulator Patches für UPS Gleitkommaarithmetik \(nur gemischter Sprache\).<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Fr**\[\[`filename`\]\]|Generiert eine Quelle sbr\-datei Browser.|  
|**\/FR**\[\[`filename`\]\]|Generiert ein erweitertes Form einer Quelle sbr\-datei Browser.|  
|**\/Gc**|Gibt Verwendung von Fortran\- oder Pascal\-Format Funktion aufrufen und den Benennungskonventionen an.  Identisch mit **OPTION LANGUAGE:PASCAL**.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Gd**|Gibt Verwendung von Funktionen in C\-Format aufrufen und Benennungskonventionen an.  Identisch mit **OPTION LANGUAGE:C**.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/GZ**|Gibt Verwendung \_\_stdcall Funktion aufrufen und den Benennungskonventionen an.  Identisch mit **OPTION LANGUAGE:STCALL**.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/H** `number`|Schränkt externer Namen zu beträchtlichen Zeichen der Zahl ein.  Der Standardwert ist 31 Zeichen.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/help**|QuickHelp um Hilfe in Rufung ML.|  
|**\/I** `pathname`|Legt den Pfad zur Includedatei fest.  Ein maximal 10 **\/I** Optionen ist zulässig.|  
|**\/nologo**|Unterdrückt Nachrichten für erfolgreiche Assembly.|  
|**\/omf**|Generiert Typ des Objektmodul\-Dateiformats OMF \(\) des Objektmoduls.  **\/omf** bedeutet **\/c**. ML.exe unterstützt nicht das Verknüpfen von OMF\-Objekten.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Sa**|Aktiviert alle verfügbaren Informationen aufgelistet werden.|  
|**\/safeseh**|Markiert das Objekt entweder als enthaltenden keiner Ausnahmehandler oder enthaltenden aus Ausnahmehandlern, die alle mit [.SAFESEH](../../assembler/masm/dot-safeseh.md)deklariert werden.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Sf**|Fügt die Ausführung der ersten hinzu, die Listendatei auflistet.|  
|**\/Sl** `width`|Legt die Linienstärke aus den Listen Quellspalten in Zeichen pro Zeile fest.  Bereich liegt zwischen 60 und 255 oder 0.  Der Standardwert ist 0.  Identisch mit [PAGE](../../assembler/masm/page.md) Breite.|  
|**\/Sn**|Stellt Symboltabelle ab, sofern, Listen erzeugend.|  
|**\/Sp** `length`|Legt die Länge des Seiten in den Listen Quellspalten der Zeilen pro Seite festlegen.  Bereich liegt zwischen 10 und 255 oder 0.  Der Standardwert ist 0.  Identisch mit [PAGE](../../assembler/masm/page.md) Länge.|  
|**\/Ss** `text`|Gibt Text für Listen Quellspalten an.  Identisch mit [UNTERTITEL](../../assembler/masm/subtitle.md) Text.|  
|**\/St** `text`|Gibt den Listen Quellspalten Namen an.  Identisch mit [Umbrechen von](../../assembler/masm/title.md) Text.|  
|**\/Sx**|Schaltet falsche Bedingungen in der Auflistung ein.|  
|**\/Ta** `filename`|Rekonstruiert Quelldatei zusammen, deren Name nicht mit der .asm\-Erweiterung beendet.|  
|**\/w**|Identisch mit **\/W0\/WX**.|  
|**\/W** `level`|Die Warnstufe, in der `level` \= 0, 1, 2 oder 3 festgelegt wird.|  
|**\/WX**|Gibt einen Fehlercode zurück, wenn Warnungen generiert wurden.|  
|**\/X**|Ignoriert Momentaufnahme für die EINSCHLIESSUNGS Pfad.|  
|**\/Zd**|Generiert Zeilennummerninformationen in der Objektdatei.|  
|**\/Zf**|Führt alle Symbol öffentlich.|  
|**\/Zi**|Generiert CodeView\-Informationen in der Objektdatei.|  
|**\/Zm**|Aktiviert**M510** Option für maximale Kompatibilität mit MASM 5.1.<br /><br /> Nicht verfügbar in ml64.exe.|  
|**\/Zp**\[\[`alignment`\]\]|strukturen Pack auf der angegebenen Byte beschränkt.  Der `alignment` kann 1, 2 oder 4 sein.|  
|**\/Zs**|Führt nur eine Syntaxprüfung aus.|  
|**\/?**|Zeigt eine Zusammenfassung der ML\-Befehlszeilensyntax an.|  
  
 `filename`  
 Der Name der Datei.  
  
 `linkoptions`  
 Die Optionen für den Link.  Weitere Informationen finden Sie unter [Linkeroptionen](../../build/reference/linker-options.md).  
  
## Hinweise  
 Einige Befehlszeilenoptionen zu ML und SENSITIVE Platzierung ML64 sind.  Zum Beispiel ML64 und ML da einige Optionen **\/c** akzeptieren, müssen alle entsprechenden **\/Fo** Optionen vor **\/c**angegeben werden.  Im folgenden Befehlszeilenbeispiel wird eine Objektdatei Spezifikation Spezifikation für jede Assemblydatei:  
  
 **ml.exe \/Fo a1.obj \/c a.asm \/Fo b1.obj \/c b.asm**  
  
## Umgebungsvariablen  
  
|Variable|Beschreibung|  
|--------------|------------------|  
|INCLUDE|Gibt Suchpfad für Includedateien an.|  
|ML|Gibt die Befehlszeilenoptionen an.|  
|TMP|Gibt den Pfad für temporäre Dateien an.|  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)