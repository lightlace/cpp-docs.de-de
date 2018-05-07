---
title: Compilerfehler Warnungen C4000 über C4199 | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4000
- C4002
- C4006
- C4008
- C4019
- C4023
- C4025
- C4026
- C4027
- C4030
- C4033
- C4035
- C4036
- C4038
- C4041
- C4045
- C4051
- C4052
- C4053
- C4057
- C4060
- C4063
- C4064
- C4065
- C4066
- C4068
- C4069
- C4075
- C4076
- C4077
- C4080
- C4081
- C4085
- C4086
- C4087
- C4097
- C4102
- C4109
- C4112
- C4115
- C4117
- C4119
- C4120
- C4122
- C4123
- C4125
- C4130
- C4131
- C4132
- C4137
- C4138
- C4141
- C4143
- C4145
- C4152
- C4153
- C4155
- C4158
- C4160
- C4161
- C4163
- C4164
- C4165
- C4166
- C4167
- C4168
- C4174
- C4175
- C4176
- C4177
- C4178
- C4179
- C4180
- C4181
- C4182
- C4185
- C4186
- C4187
- C4188
- C4189
- C4191
- C4193
- C4194
- C4195
- C4196
- C4199
dev_langs:
- C++
ms.assetid: 426f495a-43af-4906-ad2b-6e5822c09965
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f99b7be82ccd786bf2b2a5d18ed24a3e3211ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warnings-c4000-through-c4199"></a>Compilerfehler Warnungen C4000 über C4199

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der warnungsmeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>Warnmeldungen

|Warnung|Meldung|
|-------------|-------------|
|Compilerwarnung C4000|UNBEKANNTE WARNUNG<br /><br /> Wählen Sie den technischen Supportbefehl Visual C++<br /><br /> Menü "Hilfe", oder öffnen Sie die Hilfedatei für Weitere Informationen|
|[Compilerwarnung (Ebene 4) C4001](../../error-messages/compiler-warnings/compiler-warning-level-4-c4001.md)|nicht dem Standard entsprechende Erweiterung "einzeiliger Kommentar" wurde verwendet.|
|Compilerwarnung (Stufe 1) C4002|Zu viele übergebene Parameter für das Makro "Bezeichner"|
|[Compilerwarnung (Ebene 1) C4003](../../error-messages/compiler-warnings/compiler-warning-level-1-c4003.md)|Nicht genügend tatsächliche Parameter für das Makro 'identifier'|
|[Compilerwarnung (Ebene 1) C4005](../../error-messages/compiler-warnings/compiler-warning-level-1-c4005.md)|'Bezeichner': Neudefinition von Makros|
|Compilerwarnung (Stufe 1) C4006|#undef erwartet einen Bezeichner|
|[Compilerwarnung (Ebene 2) C4007](../../error-messages/compiler-warnings/compiler-warning-level-2-c4007.md)|'Funktion': 'Attribut' muss|
|Compilerwarnung (Stufe 3) C4008|'Funktion': 'Attribut'-Attribut wird ignoriert|
|[Compilerwarnung (Ebene 1) C4010](../../error-messages/compiler-warnings/compiler-warning-level-1-c4010.md)|einzeiliger Kommentar enthält Zeilenfortsetzungszeichen|
|[Compilerwarnung (Ebene 3) C4013](../../error-messages/compiler-warnings/compiler-warning-level-3-c4013.md)|'Funktion' nicht definiert. Annahme, dass "extern" Int zurückgeben|
|[Compilerwarnung (Ebene 1) C4015](../../error-messages/compiler-warnings/compiler-warning-level-1-c4015.md)|'Bezeichner': Typ der Bitfeld muss ganzzahlig sein|
|[Compilerwarnung (Ebene 3) C4018](../../error-messages/compiler-warnings/compiler-warning-level-3-c4018.md)|'Ausdruck': Konflikt zwischen signed/unsigned|
|Compilerwarnung (Stufe 4) C4019|Leere Anweisung im globalen Gültigkeitsbereich|
|[Compilerwarnung (Ebene 1) C4020](../../error-messages/compiler-warnings/compiler-warning-level-1-c4020.md)|'Funktion': zu viele aktuelle Parameter|
|[Compilerwarnung (Ebene 1) C4022](../../error-messages/compiler-warnings/compiler-warning-level-1-c4022.md)|'Funktion': Zeiger nicht übereinstimmende für übergebener Parameter 'Parameternummer'|
|Compilerwarnung (Stufe 1) C4023|'Funktion': Zeiger auf Funktion ohne Prototyp übergeben: Parameter "Parameter_number"|
|[Compilerwarnung (Ebene 1) C4024](../../error-messages/compiler-warnings/compiler-warning-level-1-c4024.md)|'Funktion': unterschiedliche Typen für formale und tatsächliche Parameter "Parameter_number"|
|Compilerwarnung (Stufe 1) C4025|'Funktion': Zeiger auf die Funktion mit Variablen Argumenten übergeben: Parameter "Parameter_number"|
|Compilerwarnung (Stufe 1) C4026|Funktion mit Liste formaler Parameter deklariert|
|Compilerwarnung (Stufe 1) C4027|Funktion ohne Liste formaler Parameter deklariert|
|[Compilerwarnung (Ebene 1) C4028](../../error-messages/compiler-warnings/compiler-warning-level-1-c4028.md)|formale Parameter "Parameter_number" Deklaration unterscheiden|
|[Compilerwarnung (Ebene 1) C4029](../../error-messages/compiler-warnings/compiler-warning-level-1-c4029.md)|deklarierte Liste formaler Parameter weicht von der definition|
|Compilerwarnung (Stufe 1) C4030|Die erste Liste formaler Parameter ist länger als die zweite Liste|
|[Compilerwarnung (Ebene 1) C4031](../../error-messages/compiler-warnings/compiler-warning-level-1-c4031.md)|zweite Liste formaler Parameter ist länger als die erste Liste|
|[Compilerwarnung (Ebene 4) C4032](../../error-messages/compiler-warnings/compiler-warning-level-4-c4032.md)|formaler Parameter "Parameter_number" verfügt über verschiedene Typ heraufgestuft|
|Compilerwarnung (Stufe 1) C4033|"Funktion" muss einen Wert zurückgeben|
|[Compilerwarnung (Ebene 1) C4034](../../error-messages/compiler-warnings/compiler-warning-level-1-c4034.md)|"sizeof" gibt 0 zurück.|
|Compilerwarnung (Stufe 3) C4035|'Funktion': keinen Wert zurückgibt|
|Compilerwarnung (Stufe 1) C4036|Unbenannter Typ 'Typ' als übergebener Parameter|
|Compilerwarnung (Stufe 1) C4038|"Modifizierer": Unzulässiger Klassenmodifizierer|
|Compilerwarnung (Stufe 1) C4041|Compilerlimit: Browserausgabe|
|[Compilerwarnung (Ebene 1) C4042](../../error-messages/compiler-warnings/compiler-warning-level-1-c4042.md)|'Bezeichner': Ungültige Speicherklasse hat|
|Compilerwarnung (Stufe 1) C4045|"Array": Arraygrenze überschritten|
|[Compilerwarnung (Ebene 1) C4047](../../error-messages/compiler-warnings/compiler-warning-level-1-c4047.md)|"Operator": "Bezeichner1" unterscheidet sich in Ebenen der Dereferenzierung von "Bezeichner2"|
|[Compilerwarnung (Ebene 1) C4048](../../error-messages/compiler-warnings/compiler-warning-level-1-c4048.md)|verschiedene Arrayfeldindizes: "Bezeichner1" und "Bezeichner2"|
|[Compilerwarnung (Ebene 1) C4049](../../error-messages/compiler-warnings/compiler-warning-level-1-c4049.md)|Compilerlimit: Ausgabe der Zeilennummer beenden|
|Compilerwarnung (Stufe 1) C4051|Typkonvertierung; möglicher Datenverlust|
|Compilerwarnung (Stufe 4) C4052|Unterschiedliche Funktionsdeklarationen; eine enthält variable Argumente|
|Compilerwarnung (Stufe 4) C4053|Ein void-Operand für "?:"|
|[Compilerwarnung (Ebene 1) C4055](compiler-warning-level-1-c4055.md)|"Konvertierung': von Datenzeiger '*Typ1*'zu Funktionszeiger'*Typ2*"|
|[Compilerwarnung (Ebene 2) C4056](../../error-messages/compiler-warnings/compiler-warning-level-2-c4056.md)|Überlauf in Gleitkommazahlen-Konstante|
|Compilerwarnung (Stufe 4) C4057|"Operator": "Bezeichner1" unterscheidet Dereferenzierung in leicht unterschiedliche Basistypen von 'Bezeichner2'|
|Warnung C4060|Switch-Anweisung enthält keine 'Case' oder 'Default'-Beschriftungen|
|[Compilerwarnung (Ebene 4) C4061](../../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md)|Enumerator 'Identifier' in Switch Enumeration 'Enumeration' wird nicht explizit von einer Case-Bezeichnung behandelt.|
|[Compilerwarnung (Ebene 4) C4062](../../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md)|Enumerator 'identifier' in switch (enum) 'enumeration' wird nicht verarbeitet|
|Compilerfehler Warnung C4063|Case 'Bezeichner' ist kein gültiger Wert für den Schalter der Enumeration 'Enumeration'|
|Warnung C4064|Switch unvollständige Enumeration 'Enumeration'|
|Warnung C4065|Switch-Anweisung enthält 'Default', aber keine 'Case'-Beschriftungen|
|Compilerwarnung (Stufe 3) C4066|Mit Ausnahme des ersten Zeichens werden die Zeichen in einer "breiten" Zeichenkonstante ignoriert|
|[Compilerwarnung (Ebene 1) C4067](../../error-messages/compiler-warnings/compiler-warning-level-1-c4067.md)|Unerwartetes Token nach Präprozessordirektive - Zeilenvorschub erwartet|
|Compilerwarnung (Stufe 1) C4068|Unbekanntes Pragma|
|Compilerwarnung C4069|long Double ist die gleiche Genauigkeit wie double|
|[Compilerwarnung (Ebene 3) C4073](../../error-messages/compiler-warnings/compiler-warning-level-3-c4073.md)|Fügen Sie in der Bibliothek Initialisierungsbereich Initialisierer|
|[Compilerwarnung (Ebene 1) C4074](../../error-messages/compiler-warnings/compiler-warning-level-1-c4074.md)|Initialisierer gelagerte Compiler reserviert Initialisierungsbereich|
|Compilerwarnung (Stufe 1) C4075|Initialisierungen stehen in nicht erkanntem Initialisierungsbereich|
|Compilerwarnung (Stufe 1) C4076|"Type_modifier": kann nicht mit Typ "Typname" verwendet werden|
|Compilerwarnung (Stufe 1) C4077|Unbekannte check_stack-Option|
|[Compilerwarnung (Ebene 1) C4079](../../error-messages/compiler-warnings/compiler-warning-level-1-c4079.md)|Unerwartetes Token "Token"|
|Compilerwarnung (Stufe 1) C4080|Bezeichner für Segmentnamen erwartet; "Symbol" gefunden|
|Compilerwarnung (Stufe 1) C4081|"Ttoken1" erwartet'; "Token2" gefunden|
|[Compilerwarnung (Ebene 1) C4083](../../error-messages/compiler-warnings/compiler-warning-level-1-c4083.md)|'token' erwartet Bezeichner "Identifier" gefunden|
|Compilerwarnung (Stufe 1) C4085|Pragma-Parameter "on" oder "off" erwartet|
|Compilerwarnung (Stufe 1) C4086|Pragma-Parameter "1", "2", "4", "8" oder "16" erwartet|
|Compilerwarnung (Stufe 1) C4087|'Funktion': mit "void"-Parameterliste deklariert|
|[Compilerwarnung (Ebene 1) C4088](../../error-messages/compiler-warnings/compiler-warning-level-1-c4088.md)|'Funktion': Zeiger übereinstimmende Datentypen in der tatsächlichen Parameter "Parameter_number", "Parameter_number" einen formalen Parameter|
|[Compilerwarnung (Ebene 1) C4089](../../error-messages/compiler-warnings/compiler-warning-level-1-c4089.md)|'Funktion': unterschiedliche Typen in übergebener Parameter "Parameter_number", "Parameter_number" einen formalen Parameter|
|[Compilerwarnung (Ebene 1) C4090](../../error-messages/compiler-warnings/compiler-warning-level-1-c4090.md)|'Operation': unterschiedliche 'Modifizierer'-Qualifizierer|
|[Compilerwarnung (Ebene 1) C4091](../../error-messages/compiler-warnings/compiler-warning-level-1-c4091.md)|Schlüsselwort ":"Typ"Links ignoriert werden, wenn keine Variable deklariert wurde|
|[Compilerwarnung (Ebene 4) C4092](../../error-messages/compiler-warnings/compiler-warning-level-4-c4092.md)|"sizeof" gibt "unsigned long"|
|[Compilerwarnung (Ebene 2) C4094](../../error-messages/compiler-warnings/compiler-warning-level-2-c4094.md)|Unbenanntes 'token' deklariert keine Symbole|
|[Compilerwarnung (Ebene 1) C4096](../../error-messages/compiler-warnings/compiler-warning-level-1-c4096.md)|'Bezeichner': Schnittstelle ist nicht mit einem COM-Schnittstelle wird nicht an IDL ausgegeben werden|
|Compilerwarnung (Stufe 1) C4097|Erwarteter pragma-Parameter sollte "restore" oder "off" sein|
|[Compilerwarnung (Ebene 1) C4098](../../error-messages/compiler-warnings/compiler-warning-level-1-c4098.md)|'Funktion': 'void'-Funktion einen Wert zurückgeben|
|[Compilerwarnung (Ebene 2) C4099](../../error-messages/compiler-warnings/compiler-warning-level-2-c4099.md)|'Bezeichner': Typnamen, die mit "object_type1" nun gesehen, mit "object_type2" für die erstmalige Sichtbarkeit|
|[Compilerwarnung (Ebene 4) C4100](../../error-messages/compiler-warnings/compiler-warning-level-4-c4100.md)|"Bezeichner": Unreferenzierter formaler Parameter|
|[Compilerwarnung (Ebene 3) C4101](../../error-messages/compiler-warnings/compiler-warning-level-3-c4101.md)|"Bezeichner": Unreferenzierte lokale Variable|
|Compilerwarnung (Stufe 3) C4102|'Bezeichnung': Unreferenzierte Marke|
|[Compilerwarnung (Ebene 1) C4103](../../error-messages/compiler-warnings/compiler-warning-level-1-c4103.md)|'Dateiname': Ausrichtung, die geändert, nachdem die Header, einschließlich möglicherweise aufgrund fehlender #pragma pack(pop)|
|Compilerwarnung (Stufe 1) C4109|Unerwarteter Bezeichner "identifier"|
|Compilerwarnung (Stufe 1) C4112|#line erfordert eine Ganzzahl zwischen 1 und "Line_count"|
|[Compilerwarnung (Ebene 1) C4113](../../error-messages/compiler-warnings/compiler-warning-level-1-c4113.md)|"Bezeichner1" unterscheidet sich in Parameterlisten von "Bezeichner2"|
|[Compilerwarnung (Ebene 1) C4114](../../error-messages/compiler-warnings/compiler-warning-level-1-c4114.md)|Der gleiche Typqualifizierer wurde mehrmals verwendet|
|Compilerwarnung (Stufe 1 und Stufe 4) C4115|'Typ': benannte Typdefinition in Klammern|
|[Compilerwarnung (Ebene 1) C4116](../../error-messages/compiler-warnings/compiler-warning-level-1-c4116.md)|Unbenannte Typdefinition in runden Klammern|
|Compilerwarnung (Stufe 1) C4117|Makroname 'Name' ist reserviert, 'Befehl' wird ignoriert|
|Compilerwarnung (Stufe 1) C4119|Unterschiedliche Basissegmente angegeben, "Basis1" und "Basis2"|
|Compilerwarnung (Stufe 1) C4120|Konflikt zwischen normalem und segmentbasiertem Zeiger|
|[Compilerwarnung (Ebene 4) C4121](../../error-messages/compiler-warnings/compiler-warning-level-4-c4121.md)|'Symbol': Ausrichtung eines Elements wurde pragma|
|Compilerwarnung (Stufe 1) C4122|"Function": alloc_text ist nur für Funktionen mit C-Bindung anwendbar|
|Compilerwarnung (Stufe 1) C4123|unterschiedliche Basisausdrücke angegeben|
|[Compilerwarnung (Ebene 1) C4124](../../error-messages/compiler-warnings/compiler-warning-level-1-c4124.md)|__fastcall mit stapelüberprüfung ist ineffizient|
|Compilerwarnung (Stufe 4) C4125|Dezimale Ziffer beendet oktale Escapesequenz|
|[Compilerwarnung (Ebene 4) C4127](../../error-messages/compiler-warnings/compiler-warning-level-4-c4127.md)|Bedingter Ausdruck ist konstant|
|[Compilerwarnung (Ebene 1) C4129](../../error-messages/compiler-warnings/compiler-warning-level-1-c4129.md)|"Character": Unbekannte Escape-Zeichensequenz|
|Compilerwarnung (Stufe 4) C4130|'Operator': logische Operation mit Adresse einer Zeichenfolgenkonstanten|
|Compilerwarnung (Stufe 4) C4131|'Funktion': verwendet Deklarator für altes Format|
|Compilerwarnung (Stufe 4) C4132|'Object': Konstantes Objekt sollte initialisiert werden|
|[Compilerwarnung (Ebene 3) C4133](../../error-messages/compiler-warnings/compiler-warning-level-3-c4133.md)|'Ausdruck': Inkompatible Typen - von "Typ1" in "Typ2"|
|Compilerwarnung C4137|'Funktion': kein Rückgabewert von Gleitkomma-Funktion|
|Compilerwarnung (Stufe 1) C4138|"*/" wurde außerhalb des Kommentars gefunden|
|Compilerwarnung (Stufe 1) C4141|"Modifizierer": mehrmals verwendet|
|[Compilerwarnung (Ebene 1) C4142](../../error-messages/compiler-warnings/compiler-warning-level-1-c4142.md)|keine Auswirkungen Neudefinition des Typs|
|Compilerwarnung (Stufe 1) C4143|Pragma "same_seg" wird nicht unterstützt; reservieren Sie Segmente mit __based|
|[Compilerwarnung (Ebene 1) C4144](../../error-messages/compiler-warnings/compiler-warning-level-1-c4144.md)|'Ausdruck': Relationaler Ausdruck als Schalterausdruck|
|Compilerwarnung (Stufe 1) C4145|"Ausdruck1": Relationaler Ausdruck als Schalterausdruck; mögliche Verwechslung mit "Ausdruck2"|
|[Compilerwarnung (Ebene 2) C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|Typ ohne Vorzeichen, wurde ein unäres minus-Operator angewendet.|
|[Compilerwarnung (Ebene 2) C4150](../../error-messages/compiler-warnings/compiler-warning-level-2-c4150.md)|Löschen eines Zeigers auf unvollständigen Typ 'Typ'; keinen Destruktor wird aufgerufen|
|Compilerwarnung (Stufe 4) C4152|nicht dem Standard entsprechende Erweiterung Funktion/datenzeigerkonvertierung im Ausdruck|
|Compilerwarnung (Stufe 1) C4153|Funktions-/Datenzeigerkonvertierung im Ausdruck|
|[Compilerwarnung (Ebene 1) C4154](../../error-messages/compiler-warnings/compiler-warning-level-1-c4154.md)|Löschen eines Arrayausdrucks; Konvertierung in Zeiger|
|Compilerwarnung (Stufe 1) C4155|Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "delete"|
|[Compilerwarnung (Ebene 2) C4156](../../error-messages/compiler-warnings/compiler-warning-level-2-c4156.md)|Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "Delete". Arrayform ersetzt|
|[Compilerwarnung (Ebene 1) C4157](../../error-messages/compiler-warnings/compiler-warning-level-1-c4157.md)|Pragma wurde vom C-Compiler ignoriert.|
|Compilerwarnung (Stufe 1) C4158|Annahme von #pragma Pointers_to_members (Full_generality, "Inheritance_type")|
|[Compilerwarnung (Ebene 3) C4159](../../error-messages/compiler-warnings/compiler-warning-level-3-c4159.md)|#pragma "pragma'(pop,...): wurde per pop ausgelesen zuvor per push abgelegten Bezeichner"Identifier"|
|Compilerwarnung (Stufe 1) C4160|#pragma "pragma'(pop,...): zuvor per push abgelegten Bezeichner"Identifier"wurde nicht gefunden|
|Compilerwarnung (Stufe 3) C4161|#pragma "pragma'(pop...): mehr POP-als Push-Vorgänge|
|[Compilerwarnung (Ebene 1) C4162](../../error-messages/compiler-warnings/compiler-warning-level-1-c4162.md)|'Bezeichner': keine Funktion mit C-Bindung gefunden|
|Compilerwarnung (Stufe 1) C4163|'Bezeichner': nicht als systeminterne Funktion verfügbar|
|Compilerwarnung (Stufe 1) C4164|"Function": systeminterne Funktion nicht deklariert|
|Compilerwarnung (Stufe 1) C4165|'HRESULT' wird "Bool" konvertiert sind Sie sicher, dass dies gewünscht ist?|
|Compilerwarnung (Stufe 1) C4166|Unzulässige Aufrufkonvention für Konstruktor/Destruktor|
|Compilerwarnung (Stufe 1) C4167|'Funktion': nur als systeminterne Funktion verfügbar|
|Compilerwarnung (Stufe 1) C4168|Compilerlimit: nicht genügend Debuggertypen, löschen Sie Programmdatenbank 'Datenbank' und neu erstellen|
|[Compilerwarnung (Ebene 1) C4172](../../error-messages/compiler-warnings/compiler-warning-level-1-c4172.md)|Adresse einer lokalen Variable oder temporäre zurückgeben|
|Compilerwarnung (Stufe 1) C4174|'Name': nicht als #pragma-Komponente verfügbar|
|Compilerwarnung (Stufe 1) C4175|#pragma Component(browser, on): Browserinformationen muss zunächst in der Befehlszeile angegeben werden|
|Compilerwarnung (Stufe 1) C4176|"Subcomponent": Unbekannte Unterkomponente bei #pragma Component Browser|
|Compilerwarnung (Stufe 1) C4177|#pragma "Pragma" sollte nur im globalen Gültigkeitsbereich oder Namespacebereich verwendet werden|
|Compilerwarnung (Stufe 1) C4178|Die case-Konstante 'Konstante' ist zu groß für den Typ des switch-Ausdrucks.|
|Compilerwarnung (Stufe 4) C4179|"//*': als analysiert '/' und ' /\*': Verwechslung mit Standardkommentaren ' / /" Kommentare|
|Compilerwarnung (Stufe 1) C4180|Auf Funktionstyp angewendeter Qualifizierer ist ohne Bedeutung; wird ignoriert|
|Compilerwarnung C4181|Qualifizierer angewendet, um den Typ verweisen; ignoriert|
|Compilerwarnung (Stufe 1) C4182|#include Schachtelungsebene ist "Nest_count" tief; Endlosschleife möglich|
|[Compilerwarnung (Ebene 1) C4183](../../error-messages/compiler-warnings/compiler-warning-level-1-c4183.md)|'Bezeichner': Rückgabetyp fehlt; Angenommen, dass eine Memberfunktion, die Rückgabe von "Int" sein|
|Compilerwarnung (Stufe 1) C4185|Das unbekannte #import-Attribut "Attribut" wird ignoriert|
|Compilerwarnung (Stufe 1) C4186|#import-Attribut 'Attribut' erfordert 'Argument_count'-Argumente. ignoriert|
|Compilerwarnung (Stufe 1) C4187|#import-Attribute 'Attribut1' und 'Attribut2' sind inkompatibel. Beide werden ignoriert.|
|Compilerwarnung (Stufe 1) C4188|Konstanter Ausdruck ist keine Ganzzahl|
|Compilerwarnung (Stufe 4) C4189|"Bezeichner": lokale Variable ist initialisiert, aber nicht auf die verwiesen wird|
|[Compilerwarnung (Ebene 1) C4190](../../error-messages/compiler-warnings/compiler-warning-level-1-c4190.md)|"Bezeichner1" C-Bindung angegeben wurde, gibt aber UDT "Bezeichner2" die mit C nicht kompatibel ist|
|Compilerwarnung (Stufe 3) C4191|' Operator/Operation': unsichere Konvertierung von 'Type_of_expression' zu "Type_required" \nCalling diese Funktion über den Ergebniszeiger kann dazu führen, dass das Programm fehlschlägt|
|[Compilerwarnung (Ebene 3) C4192](../../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)|automatisch beim Importieren einer Typbibliothek "Library" ausgeschlossen "Bezeichner"|
|Compilerwarnung (Stufe 3) C4193|#pragma warning"(POP): keine übereinstimmende""#pragma warning""|
|Compilerwarnung (Stufe 1) C4194|#pragma Start_map_region kann nicht geschachtelt werden. ignoriert|
|Compilerwarnung (Stufe 1) C4195|#pragma stop_map_region wurde ohne entsprechende #pragma Start_map_region verwendet; ignoriert|
|Compilerwarnung (Stufe 1) C4196|erwartet wurde "%$L" oder "%$L;" "%$L" gefunden|
|[Compilerwarnung (Ebene 3) C4197](../../error-messages/compiler-warnings/compiler-warning-level-3-c4197.md)|'Typ': der obersten Ebene Volatile in Typumwandlung wird ignoriert.|
|Compilerwarnung (Stufe 1, Ebene 2, Ebene 3 und Ebene 4) C4199|%s|
