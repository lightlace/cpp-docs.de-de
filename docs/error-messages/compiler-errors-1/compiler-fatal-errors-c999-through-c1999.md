---
title: Schwerwiegende Compilerfehler C999 bis C1999
ms.date: 04/21/2019
f1_keywords:
- C1034
- C1036
- C1041
- C1048
- C1063
- C1069
- C1101
- C1102
- C1105
- C1110
- C1111
- C1112
- C1114
- C1193
- C1195
- C1300
- C1301
- C1302
- C1306
- C1384
- C1451
- C1505
- C1901
helpviewer_keywords:
- C1034
- C1036
- C1041
- C1048
- C1063
- C1069
- C1101
- C1102
- C1105
- C1110
- C1111
- C1112
- C1114
- C1193
- C1195
- C1300
- C1301
- C1302
- C1306
- C1384
- C1451
- C1505
- C1901
ms.assetid: 6c8df109-7594-48ed-987a-97d9fe2b04af
ms.openlocfilehash: 395d7403ef4fe04b671a84a61d320b27ad8ad1c7
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626569"
---
# <a name="compiler-fatal-errors-c999-through-c1999"></a>Schwerwiegende Compilerfehler C999 bis C1999

In den Artikeln in diesem Abschnitt der Dokumentation wird eine Teilmenge der Fehlermeldungen erläutert, die vom Microsoft C/C++ Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Nachricht|
|-----------|-------------|
|[Schwerwiegender Fehler C999](../../error-messages/compiler-errors-1/fatal-error-c999.md)|UNBEKANNTE MELDUNG Wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen Sie die Hilfedatei für weitere Informationen.|
|[Schwerwiegender Fehler C1001](../../error-messages/compiler-errors-1/fatal-error-c1001.md)|Ein interner Fehler ist im Compiler aufgetreten.<br /> (Compilerdatei „*file*“, Zeile *number*)<br /> Vereinfachen oder ändern Sie das Programm im Umfeld der oben aufgeführten Positionen, um dieses Problem zu umgehen. Wählen Sie den technischen Supportbefehl im Visual C++-Hilfemenü, oder öffnen Sie die Hilfedatei für weitere Informationen.|
|[Schwerwiegender Fehler C1002](../../error-messages/compiler-errors-1/fatal-error-c1002.md)|Im 2. Durchlauf ist kein Heapspeicher mehr für den Compiler verfügbar.|
|[Schwerwiegender Fehler C1003](../../error-messages/compiler-errors-1/fatal-error-c1003.md)|Mehr als *number*Fehler gefunden; Kompilierung wird abgebrochen.|
|[Schwerwiegender Fehler C1004](../../error-messages/compiler-errors-1/fatal-error-c1004.md)|Unerwartetes Dateiende gefunden.|
|[Schwerwiegender Fehler C1005](../../error-messages/compiler-errors-1/fatal-error-c1005.md)|Zeichenfolge zu lang für Puffer|
|[Schwerwiegender Fehler C1007](../../error-messages/compiler-errors-1/fatal-error-c1007.md)|Unbekanntes Flag „*string*“ in „*option*“.|
|[Schwerwiegender Fehler C1008](../../error-messages/compiler-errors-1/fatal-error-c1008.md)|Keine Quelldatei angegeben|
|[Schwerwiegender Fehler C1009](../../error-messages/compiler-errors-1/fatal-error-c1009.md)|Compilerlimit: zu tiefe Schachtelung von Makros|
|[Schwerwiegender Fehler C1010](../../error-messages/compiler-errors-1/fatal-error-c1010.md)|Unerwartetes Dateiende während der Suche nach dem vorkompilierten Header. Haben Sie vergessen, der Quelle "#include \<*Datei*>" hinzuzufügen?|
|[Schwerwiegender Fehler C1012](fatal-error-c1012.md)|Fehlende zugehörige Klammer: „*character*“ fehlt.|
|[Schwerwiegender Fehler C1013](fatal-error-c1013.md)|Compilerlimit: zu viele geöffnete Klammern|
|[Schwerwiegender Fehler C1014](fatal-error-c1014.md)|Zu viele Includedateien: Tiefe = *number*|
|[Schwerwiegender Fehler C1016](fatal-error-c1016.md)|#ifdef/#ifndef: Es wurde ein Bezeichner erwartet.|
|[Schwerwiegender Fehler C1017](../../error-messages/compiler-errors-1/fatal-error-c1017.md)|Ungültiger Ausdruck für Ganzzahlkonstante|
|[Schwerwiegender Fehler C1018](fatal-error-c1018.md)|Unerwartetes #elif|
|[Schwerwiegender Fehler C1019](fatal-error-c1019.md)|Unerwartetes #else|
|[Schwerwiegender Fehler C1020](fatal-error-c1020.md)|Unerwartetes #endif|
|[Schwerwiegender Fehler C1021](fatal-error-c1021.md)|Ungültiger Präprozessorbefehl „*string*“.|
|[Schwerwiegender Fehler C1022](fatal-error-c1022.md)|#endif erwartet|
|[Schwerwiegender Fehler C1023](fatal-error-c1023.md)|„*file*“: Unerwarteter Fehler im PCH. Erstellen Sie den PCH neu.|
|[Schwerwiegender Fehler C1026](../../error-messages/compiler-errors-1/fatal-error-c1026.md)|Stapelüberlauf im Parser, Programm zu komplex|
|[Schwerwiegender Fehler C1033](../../error-messages/compiler-errors-1/fatal-error-c1033.md)|Programmdatenbank „*file*“ kann nicht geöffnet werden.|
|Schwerwiegender Fehler C1034|*file*: Kein Suchpfad für Headerdateien vorhanden.|
|[Schwerwiegender Fehler C1035](fatal-error-c1035.md)|Ausdruck zu komplex. Vereinfachen Sie den Ausdruck.|
|Schwerwiegender Fehler C1036|Das vorherige Programmdatenbankformat kann nicht überschrieben werden. Löschen Sie „*file*“, und kompilieren Sie erneut.|
|[Schwerwiegender Fehler C1037](fatal-error-c1037.md)|Objektdatei „*file*“ kann nicht geöffnet werden.|
|[Schwerwiegender Fehler C1038](fatal-error-c1038.md)|Compilerlimit: „*function*“: Ablaufsteuerung zu komplex, vereinfachen Sie die Funktion.|
|Schwerwiegender Fehler C1041|Programmdatenbank „*file*“ kann nicht geöffnet werden; verwenden Sie /FS, wenn mehrere CL.EXE in dieselbe PDB-Datei schreiben.|
|[Schwerwiegender Fehler C1045](fatal-error-c1045.md)|Compilerlimit: zu tiefe Schachtelung von Bindungsangaben|
|[Schwerwiegender Fehler C1046](../../error-messages/compiler-errors-1/fatal-error-c1046.md)|Compilerlimit: *structure* zu tief geschachtelt.|
|[Schwerwiegender Fehler C1047](fatal-error-c1047.md)|Die Objekt- oder Bibliotheksdatei „*file*“ wurde mit einem älteren Compiler als andere Objekte erstellt. Erstellen Sie die alten Objekte und Bibliotheken neu.|
|Schwerwiegender Fehler C1048|Unbekannte Option „*string*“ in „*option*“.|
|[Schwerwiegender Fehler C1049](fatal-error-c1049.md)|Ungültiges numerisches Argument „*value*“.|
|[Schwerwiegender Fehler C1051](../../error-messages/compiler-errors-1/fatal-error-c1051.md)|Programmdatenbankdatei „*file*“ hat ein veraltetes Format. Löschen Sie sie, und starten Sie die Kompilierung erneut.|
|[Schwerwiegender Fehler C1052](fatal-error-c1052.md)|die Programm Datenbankdatei "*Dateiname*" wurde vom Linker mit/Debug: fastlink; generiert. der Compiler kann solche PDB-Dateien nicht aktualisieren. Löschen Sie Sie, oder verwenden Sie/FD, um einen anderen PDB-Dateinamen anzugeben.|
|[Schwerwiegender Fehler C1053](fatal-error-c1053.md)|„*function*“: Funktion ist zu groß.|
|[Schwerwiegender Fehler C1054](../../error-messages/compiler-errors-1/fatal-error-c1054.md)|Compilerlimit: zu tiefe Schachtelung von Initialisierungen|
|[Schwerwiegender Fehler C1055](../../error-messages/compiler-errors-1/fatal-error-c1055.md)|Compilerlimit: keine weiteren Schlüssel|
|[Schwerwiegender Fehler c1057](../../error-messages/compiler-errors-1/fatal-error-c1057.md)|Unerwartetes Dateiende bei der Erweiterung eines Makros|
|[Schwerwiegender Fehler C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)|Kein verfügbarer Speicher mehr im Heap|
|[Schwerwiegender Fehler C1061](../../error-messages/compiler-errors-1/fatal-error-c1061.md)|Compilerlimit: zu tiefe Schachtelung von Blöcken|
|Schwerwiegender Fehler C1063|Compilerlimit: Stapelüberlauf des Compilers|
|[Schwerwiegender Fehler C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md)|Compilerlimit: Überlauf des internen Puffers durch Token|
|[Schwerwiegender Fehler C1065](../../error-messages/compiler-errors-1/fatal-error-c1065.md)|Compilerlimit: keine weiteren Tags|
|[Schwerwiegender Fehler C1067](../../error-messages/compiler-errors-1/fatal-error-c1067.md)|Compilerlimit: Die Größenbeschränkung von 64 KB für Typeneinträge wurde überschritten.|
|[Schwerwiegender Fehler C1068](fatal-error-c1068.md)|Die Datei „*file*“ kann nicht geöffnet werden.|
|Schwerwiegender Fehler C1069|Compilerbefehlszeile kann nicht gelesen werden|
|[Schwerwiegender Fehler C1070](fatal-error-c1070.md)|Fehlende Zuordnung von #if und #endif in Datei „*file*“.|
|[Schwerwiegender Fehler C1071](../../error-messages/compiler-errors-1/fatal-error-c1071.md)|Unerwartetes Dateiende innerhalb eines Kommentars|
|[Schwerwiegender Fehler C1073](../../error-messages/compiler-errors-1/fatal-error-c1073.md)|Interner Fehler im Zusammenhang mit der inkrementellen Kompilierung (Compilerdatei „*file*“, Zeile *number*).|
|[Schwerwiegender Fehler C1074](fatal-error-c1074.md)|"IDB" ist eine ungültige Erweiterung für die PDB-Datei: *file*.|
|[Schwerwiegender Fehler C1075](../../error-messages/compiler-errors-1/fatal-error-c1075.md)|Keine Entsprechung für das linke Element *token* am Dateiende gefunden.|
|[Schwerwiegender Fehler C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)|Compilerlimit: Interne Heapgrenze erreicht; Verwenden Sie /Zm, um eine höhere Grenze anzugeben|
|[Schwerwiegender Fehler C1077](fatal-error-c1077.md)|Compilerlimit: Es können nicht mehr als *number* Befehlszeilenoptionen angegeben werden.|
|[Schwerwiegender Fehler C1079](../../error-messages/compiler-errors-1/fatal-error-c1079.md)|Compilerlimit: maximale Größe für PCH-Datei überschritten|
|[Schwerwiegender Fehler C1080](../../error-messages/compiler-errors-1/fatal-error-c1080.md)|Compilerlimit: Befehlszeilenoption überschreitet die Grenze von *number* Zeichen.|
|[Schwerwiegender Fehler C1081](../../error-messages/compiler-errors-1/fatal-error-c1081.md)|„*file*“: Dateiname zu lang.|
|[Schwerwiegender Fehler C1082](fatal-error-c1082.md)|Die *type* -Datei kann nicht geschlossen werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1083](../../error-messages/compiler-errors-1/fatal-error-c1083.md)|Die *type* -Datei kann nicht geöffnet werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1084](../../error-messages/compiler-errors-1/fatal-error-c1084.md)|Die *type* -Datei kann nicht gelesen werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1085](../../error-messages/compiler-errors-1/fatal-error-c1085.md)|Die *type* -Datei kann nicht geschrieben werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1086](fatal-error-c1086.md)|Die *type* -Datei kann nicht durchsucht werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1087](fatal-error-c1087.md)|Die *type* -Datei kann nicht ermittelt werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1088](fatal-error-c1088.md)|Die *type* -Datei kann nicht gelöscht werden: „*file*“: *message*.|
|[Schwerwiegender Fehler C1089](fatal-error-c1089.md)|Die *type* -Datei kann nicht verkleinert werden: „*file*“: *message*.|
|Schwerwiegender Fehler C1090|Fehler beim Aufruf der PDB-API, Fehlercode „*code*“: „*message*“.|
|[Schwerwiegender Fehler C1091](fatal-error-c1091.md)|Compilerlimit: Die Zeichenfolge überschreitet die Länge um *number* Bytes.|
|[Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)|Bearbeiten und Fortfahren unterstützt keine Änderungen an Datentypen. Build erforderlich|
|[Schwerwiegender Fehler C1093](../../error-messages/compiler-errors-1/fatal-error-c1093.md)|Fehler beim API-Aufruf von „*function*“ in „*HRESULT*“: „*description*“.|
|[Schwerwiegender Fehler C1094](../../error-messages/compiler-errors-1/fatal-error-c1094.md)|„-Zm*number*“: Die Befehlszeilenoption stimmt nicht mit dem Wert überein, der zum Erstellen des vorkompilierten Headers verwendet wurde („-Zm*number*“).|
|[Schwerwiegender Fehler C1098](fatal-error-c1098.md)|Nicht übereinstimmende Version in der Engine für Bearbeiten und Fortfahren|
|[Schwerwiegender Fehler C1099](fatal-error-c1099.md)|Kompilierungsabbruch durch Engine für Bearbeiten und Fortfahren|
|[Schwerwiegender Fehler C1100](fatal-error-c1100.md)|OLE kann nicht initialisiert werden: *error*.|
|Schwerwiegender Fehler C1101|Der Handler kann für das Attribut „*identifier*“ nicht erstellt werden.|
|Schwerwiegender Fehler C1102|Initialisierung konnte nicht durchgeführt werden: *error*.|
|[Schwerwiegender Fehler C1103](fatal-error-c1103.md)|Schwerwiegender Fehler beim Importieren der ProgID: „*message*“.|
|[Schwerwiegender Fehler C1104](fatal-error-c1104.md)|Schwerwiegender Fehler beim Importieren der LibID: „*message*“.|
|Schwerwiegender Fehler C1105|*message*: *error*|
|[Schwerwiegender Fehler C1107](../../error-messages/compiler-errors-1/fatal-error-c1107.md)|Die Assembly „*assembly*“ wurde nicht gefunden: Geben Sie den Assemblysuchpfad an, indem Sie /AI verwenden oder die Umgebungsvariable LIBPATH festlegen.|
|[Schwerwiegender Fehler C1108](fatal-error-c1108.md)|DLL konnte nicht gefunden werden: „*file*“.|
|[Schwerwiegender Fehler C1109](fatal-error-c1109.md)|„*symbol*“ konnte nicht in DLL „*file*“ gefunden werden.|
|Schwerwiegender Fehler C1110|Zu viele geschachtelte Vorlagen-/generische Definitionen.|
|Schwerwiegender Fehler C1111|Zu viele geschachtelte Vorlagen-/generische Parameter.|
|Schwerwiegender Fehler C1112|Compilerlimit: `'number`“ Makroargumente zu viel; nur *number* sind zulässig.|
|[Schwerwiegender Fehler C1113](../../error-messages/compiler-errors-1/fatal-error-c1113.md)|#using-Fehler bei „*file*“.|
|Schwerwiegender Fehler C1114|„*file*“: WinRT unterstützt nicht #using von einer verwalteten Assembly.|
|[Schwerwiegender Fehler C1120](../../error-messages/compiler-errors-1/fatal-error-c1120.md)|Fehler bei Aufruf von GetProcAddress für „*function*“.|
|[Schwerwiegender Fehler C1121](../../error-messages/compiler-errors-1/fatal-error-c1121.md)|Fehler beim Aufruf von CryptoAPI.|
|[Schwerwiegender Fehler C1126](../../error-messages/compiler-errors-1/fatal-error-c1126.md)|Automatische Speicherbelegung überschreitet *size*.|
|[Schwerwiegender Fehler C1128](../../error-messages/compiler-errors-1/fatal-error-c1128.md)|Die Anzahl von Abschnitten hat das Formatierungslimit der Objektdatei überschritten: Kompilieren mit /bigobj.|
|[Schwerwiegender Fehler C1189](../../error-messages/compiler-errors-1/fatal-error-c1189.md)|#error: *message*.|
|[Schwerwiegender Fehler C1190](fatal-error-c1190.md)|Für verwalteten Zielcode ist eine /clr-Option erforderlich.|
|[Schwerwiegender Fehler C1191](../../error-messages/compiler-errors-1/fatal-error-c1191.md)|„*file*“ kann nur für globalen Gültigkeitsbereich importiert werden.|
|[Schwerwiegender Fehler C1192](../../error-messages/compiler-errors-1/fatal-error-c1192.md)|#using-Fehler bei „*file*“.|
|Schwerwiegender Fehler C1193|Ein Fehler, der in *file*(*line*) erwartet wurde, konnte nicht erreicht werden.|
|Schwerwiegender Fehler C1195|Die Verwendung von /Yu und /Yc in der gleichen Befehlszeile ist nicht mit der Option /clr option kompatibel|
|[Schwerwiegender Fehler C1196](fatal-error-c1196.md)|„*identifier*“: Der in der Typbibliothek „*typelib*“ gefundene Bezeichner ist kein gültiger C++-Bezeichner.|
|[Schwerwiegender Fehler C1197](../../error-messages/compiler-errors-1/fatal-error-c1197.md)|Auf „*file*“ kann nicht verwiesen werden, da das Programm bereits auf „*file*“ verweist.|
|[Schwerwiegender Fehler C1201](fatal-error-c1201.md)|Fortfahren nach einem Syntaxfehler in der Klassenvorlagendefinition nicht möglich.|
|[Schwerwiegender Fehler C1202](fatal-error-c1202.md)|Der Kontext für einen rekursiven Typ oder eine Funktionsabhängigkeit ist zu komplex|
|[Schwerwiegender Fehler C1205](fatal-error-c1205.md)|Generics werden von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1206](fatal-error-c1206.md)|Anwendungsdomänenspezifische Daten werden von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1207](fatal-error-c1207.md)|Verwaltete Vorlagen werden von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1208](fatal-error-c1208.md)|Das Zuordnen von Verweisklassen im Stapel wird von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1209](fatal-error-c1209.md)|Friend-Assemblys werden von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1210](fatal-error-c1210.md)|/clr:pure und /clr:safe werden von der installierten Laufzeitversion nicht unterstützt.|
|[Schwerwiegender Fehler C1211](fatal-error-c1211.md)|Das benutzerdefinierte TypeForwardedTo-Attribut wird von der installierten Laufzeitversion nicht unterstützt.|
|Schwerwiegender Fehler C1300|Fehler beim Zugriff auf die Programmdatenbank *file* (*message*).|
|Schwerwiegender Fehler C1301|Fehler beim Zugriff auf die Programmdatenbank „ *file*“, ungültiges Format. Löschen Sie sie, und erstellen Sie sie neu.|
|Schwerwiegender Fehler C1302|Für das Modul „*module*“ sind in der Profildatenbank „*file*“ keine Konfigurationsdaten vorhanden.|
|[Schwerwiegender Fehler C1305](../../error-messages/compiler-errors-1/fatal-error-c1305.md)|Die Profildatenbank „*file*“ ist für eine andere Architektur vorgesehen.|
|Schwerwiegender Fehler C1306|Die letzte Änderung der Konfigurationsdatenbank“*file*“ war keine Optimierungsanalyse. Optimierungsentscheidungen sind möglicherweise veraltet.|
|[Schwerwiegender Fehler C1307](../../error-messages/compiler-errors-1/fatal-error-c1307.md)|Das Programm wurde seit dem Erfassen der Profildaten bearbeitet.|
|[Schwerwiegender Fehler C1308](../../error-messages/compiler-errors-1/fatal-error-c1308.md)|*file*: Das Verknüpfen von Assemblys wird nicht unterstützt.|
|[Schwerwiegender Fehler C1309](../../error-messages/compiler-errors-1/fatal-error-c1309.md)|Nicht übereinstimmende Versionen von C2.DLL und PGODB*ver*.DLL.|
|[Schwerwiegender Fehler C1310](fatal-error-c1310.md)|Profilgesteuerte Optimierungen sind bei OpenMP nicht verfügbar.|
|[Schwerwiegender Fehler C1311](../../error-messages/compiler-errors-1/fatal-error-c1311.md)|Das COFF-Format kann „*symbol*“ mit *number* Byte(s) einer Adresse nicht statisch initialisieren.|
|[Schwerwiegender Fehler C1312](fatal-error-c1312.md)|Zu viele bedingte Verzweigungen in Funktion.  Vereinfachen Sie den Quellcode, oder gestalten Sie ihn um.|
|[Schwerwiegender Fehler C1313](../../error-messages/compiler-errors-1/fatal-error-c1313.md)|Compilerlimit: *type* -Blöcke dürfen nicht tiefer als *number* Ebenen geschachtelt werden.|
|[Schwerwiegender Fehler C1350](../../error-messages/compiler-errors-1/fatal-error-c1350.md)|Fehler beim Laden der DLL „*file*“: DLL nicht gefunden.|
|[Schwerwiegender Fehler C1351](../../error-messages/compiler-errors-1/fatal-error-c1351.md)|Fehler beim Laden der DLL „*file*“: Inkompatible Version.|
|[Schwerwiegender Fehler C1352](fatal-error-c1352.md)|Ungültige oder beschädigte MSIL in „*function*“-Funktion aus Modul „*module*“.|
|[Schwerwiegender Fehler C1353](fatal-error-c1353.md)|Fehler beim Metadatenvorgang: Die Laufzeit ist nicht installiert, oder die Versionen stimmt nicht überein.|
|[Schwerwiegender Fehler C1382](../../error-messages/compiler-errors-1/fatal-error-c1382.md)|Die PCH-Datei „*file*“ wurde seit dem Generieren von „*obj*“ neu erstellt. Erstellen Sie dieses Objekt neu.|
|[Schwerwiegender Fehler C1383](fatal-error-c1383.md)|Die Compileroption /GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.|
|Schwerwiegender Fehler C1384|Falsche Einstellung für PGO_PATH_TRANSLATION beim Verknüpfen von „*file*“.|
|Schwerwiegender Fehler C1451|Beim Kompilieren des Aufrufdiagramms für „concurrency::parallel_for_each“ bei „*callsite*“ konnten keine Debuginformationen generiert werden.|
|Schwerwiegender Fehler C1505|Weiterverarbeitung nach Look-Ahead-Fehler im Parser nicht möglich|
|[Schwerwiegender Fehler C1506](../../error-messages/compiler-errors-1/fatal-error-c1506.md)|Weiterverarbeitung nach der Auflösung von Blöcken nicht möglich|
|[Schwerwiegender Fehler C1508](fatal-error-c1508.md)|Compilerlimit: „*function*“: Mehr als 65535 Bytes für Argumente.|
|[Schwerwiegender Fehler C1509](../../error-messages/compiler-errors-1/fatal-error-c1509.md)|Compilerlimit: Zu viele Handler für Ausnahmezustände in der Funktion „*function*“. Vereinfachen Sie die Funktion.|
|[Schwerwiegender Fehler C1510](../../error-messages/compiler-errors-1/fatal-error-c1510.md)|Die Sprachressourcendatei "clui.dll" kann nicht geöffnet werden.|
|[Schwerwiegender Fehler C1601](../../error-messages/compiler-errors-1/fatal-error-c1601.md)|Nicht unterstützter Inlineassembly-Opcode.|
|[Schwerwiegender Fehler C1602](../../error-messages/compiler-errors-1/fatal-error-c1602.md)|nicht unterstützt (systemintern)|
|[Schwerwiegender Fehler C1603](../../error-messages/compiler-errors-1/fatal-error-c1603.md)|Das Verzweigungsziel der Inlineassembly liegt um *number* Bytes außerhalb des Bereichs.|
|[Schwerwiegender Fehler C1852](fatal-error-c1852.md)|„*file*“ ist keine gültige vorkompilierte Headerdatei.|
|[Schwerwiegender Fehler C1853](../../error-messages/compiler-errors-1/fatal-error-c1853.md)|Die vorkompilierte Headerdatei „*file*“ stammt von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden Ihn von C (oder umgekehrt).|
|[Schwerwiegender Fehler C1854](../../error-messages/compiler-errors-1/fatal-error-c1854.md)|Die beim Anlegen der vorkompilierten Headerdatei in der Objektdatei „*file*“ ermittelten Informationen können nicht überschrieben werden.|
|[Schwerwiegender Fehler C1900](../../error-messages/compiler-errors-1/fatal-error-c1900.md)|Konflikt zwischen „*tool*“ Version „*number*“ und „*tool*“ Version „*number*“.|
|Schwerwiegender Fehler C1901|Interner Speicherverwaltungsfehler|
|[Schwerwiegender Fehler C1902](../../error-messages/compiler-errors-1/fatal-error-c1902.md)|Fehler im Programmdatenbank-Manager. Überprüfen Sie die Installation.|
|[Schwerwiegender Fehler C1903](fatal-error-c1903.md)|Weiterverarbeitung nach vorherigem Fehler nicht möglich; Kompilierung wird abgebrochen.|
|[Schwerwiegender Fehler C1904](fatal-error-c1904.md)|Schlechte Anbieterinteraktion: „*file*“.|
|[Schwerwiegender Fehler C1905](../../error-messages/compiler-errors-1/fatal-error-c1905.md)|Front-End und Back-End sind nicht kompatibel (muss auf den gleichenProzessor ausgerichtet sein).|

## <a name="see-also"></a>Siehe auch

[Fehler undC++ Warnungen für C/Compiler und Buildtools](../compiler-errors-1/c-cpp-build-errors.md)
