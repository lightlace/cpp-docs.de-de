---
title: "Standardm&#228;&#223;ig deaktivierte Compilerwarnungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "cl.exe-Compiler, Festlegen von Optionen"
  - "Warnungen, Compiler"
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
caps.latest.revision: 39
caps.handback.revision: "37"
ms.author: "corob"
manager: "ghogen"
---
# Standardm&#228;&#223;ig deaktivierte Compilerwarnungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Compiler schließt Warnungen ein, die standardmäßig deaktiviert sind, da die meisten Benutzer sieh nicht sehen möchten.  Sie können jedoch diese Warnungen aktivieren, indem Sie eine der folgenden Optionen verwenden.  
  
 `#pragma warning(default :`  `warning_number` `)`  
 Die angegebene Warnung \(`warning_number`\) wird auf der Standardebene aktiviert.  Dokumentation für die Warnung enthält die Standardebene der Warnung.  
  
 `#pragma warning(` `warning_level`  `:`  `warning_number` `)`  
 Die angegebene Warnung \(`warning_number`\) wird auf der angegebenen Ebene \(`warning_level`\) aktiviert.  
  
 [\/Wall](../build/reference/compiler-option-warning-level.md)  
 **\/Wall** aktiviert alle Warnungen, die standardmäßig deaktiviert sind.  
  
 Standardmäßig werden die folgenden Warnungen deaktiviert.  
  
|||  
|-|-|  
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) \(Ebene 4\)|Enumerator 'identifier' in einem Schalter der Enumeration 'enumeration' wird nicht explizit von einer case\-Bezeichnung gehandhabt|  
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) \(Ebene 3\)|Enumerator 'identifier' in switch \(enum\) 'enumeration' wird nicht verarbeitet|  
|C4191 \(Ebene 3\)|'operator\/operation': unsichere Konvertierung von 'type of expression' zu 'type required'|  
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) \(Ebene 4\)|'identifier': Umwandlung von 'type1' in 'type2', Datenverlust ist möglich|  
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) \(Ebene 4\)|'operator': Umwandlung von 'type1' in 'type2', Datenverlust ist möglich|  
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) \(Ebene 4\)|'function': Kein Funktionsprototyp angegeben: '\(\)' wird in '\(void\)' konvertiert|  
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) \(Ebene 4\)|'Funktion': Memberfunktion überschreibt keine virtuelle Memberfunktion einer Basisklasse|  
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) \(Ebene 1\)|'virtual\_function': Keine Überschreibung für virtuelle Memberfunktion der Basis 'class' verfügbar; die Funktion wird ausgeblendet|  
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) \(Ebene 3\)|'Klasse': Die Klasse verfügt über virtuelle Funktionen, der Destruktor ist jedoch nicht virtuell|  
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) \(Ebene 4\)|'function': Keine Überschreibung für virtuelle Memberfunktion der Basis 'type' verfügbar; die Funktion wird ausgeblendet|  
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) \(Ebene 3\)|'Operator': Konflikt zwischen vorzeichenloser und negativer Konstante|  
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) \(Ebene 4\)|Nicht dem Standard entsprechende Erweiterung: 'var': Die loop\-Steuerelementvariable, die in der for\-Schleife deklariert wurde, wird außerhalb des for\-Schleifenbereichs verwendet|  
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) \(Ebene 4\)|'Operator': der Ausdruck ist immer false|  
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) \(Ebene 2\)|'conversion': Verkürzung von 'type1' in 'type2'|  
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) \(Ebene 1\)|'Variable': Zeigerverkürzung von 'Typ' zu 'Typ'|  
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) \(Ebene 1\)|'Operation': Konvertierung von 'Typ1' in größeren Typ 'Typ2'|  
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) \(Ebene 4\)|'Typ' : Die Verwendung eines undefinierten Typs wurde in CLR\-Metadaten entdeckt. Das Verwenden dieses Typs führt möglicherweise zu einer Laufzeitausnahme|  
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) \(Ebene 1\)|Verhaltensänderung: 'Funktion' wird aufgerufen, in früheren Versionen wurde jedoch ein Memberoperator aufgerufen.|  
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) \(Ebene 1\)|Verhaltensänderung: 'Member1' wird anstelle von 'Member2' aufgerufen|  
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|"this": Wird in der Basisliste für den Memberinitialisierer verwendet|  
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) \(Ebene 4\)|'action': Konvertierung von 'type\_1' zu 'type\_2', Konflikt zwischen 'signed' und 'unsigned'|  
|C4370 \(Ebene 3\)|Durch bessere Verpackung wurde das Klassenlayout geändert, das vorher eine andere Compilerversion hatte|  
|C4371 \(Ebene 3\)|Durch bessere Verpackung des Members 'member' wurde das Klassenlayout geändert, das vorher eine andere Compilerversion hatte|  
|C4388 \(Ebene 4\)|Konflikt zwischen 'signed' und 'unsigned'|  
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) \(Ebene 2\)|'function': Funktionssignatur enthält Typ 'type'; C\+\+\-Objekte können nicht sicher zwischen reinem und gemischtem oder systemeigenem Code übergeben werden|  
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) \(Ebene 4\)|Fehlender Typspezifizierer \- int wird angenommen.  Hinweis: default\-int wird von C\+\+ nicht unterstützt|  
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) \(Ebene 4\)|'class1' : Das Objektlayout unter „\/vd2“ wird aufgrund der virtuellen Basis 'class2' geändert.|  
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) \(Ebene 4\)|dynamic\_cast von virtueller Basis 'class1' zu 'class2' schlägt möglicherweise bei einigen Kontexten fehl|  
|C4444 \(Ebene 3\)|Höchste Ebene '\_\_unaligned' ist in diesem Kontext nicht implementiert|  
|C4471 \(Ebene 4\)|Für eine Vorwärtsdeklaration einer Enumeration ohne Bereichseinschränkung ist ein zugrunde liegender Typ erforderlich \(int wird angenommen\).|  
|C4472 \(Ebene 1\)|'Bezeichner' ist eine systemeigene Enumeration: Fügen Sie einen Zugriffsspezifizierer \(privat\/öffentlich\) hinzu, um eine verwaltete Enumeration zu deklarieren|  
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) \(Ebene 4\)|'Funktion': Nicht referenzierte Inlinefunktion wurde entfernt|  
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) \(Ebene 4\)|'type name': Der Typenname ist größer als das Metadatenlimit von 'limit'\-Zeichen|  
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) \(Ebene 1\)|Ausdruck vor dem Komma wird als Funktion ausgewertet, der eine Argumentliste fehlt|  
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) \(Ebene 1\)|Funktionsaufruf vor dem Komma ohne Argumentliste|  
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) \(Ebene 1\)|'Operator': Operator vor dem Komma hat keine Auswirkungen; Operator mit Nebeneffekten erwartet|  
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) \(Ebene 1\)|Ausdruck vor dem Komma hat keine Auswirkung; es wurde ein Ausdruck mit Nebeneffekt erwartet|  
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) \(Ebene 1\)|'operator': Operator vor dem Komma hat keine Auswirkungen. War 'operator' beabsichtigt?|  
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) \(Ebene 1\)|Der Ausdruck hat keine Auswirkungen; Ausdruck mit Nebeneffekten erwartet|  
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) \(Ebene 3\)|'\_\_assume' enthält den Effekt 'Effekt'|  
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) \(Ebene 4\)|Information: Die catch\(...\)\-Semantik wurde gegenüber Visual C\+\+ 7.1 geändert; strukturierte Ausnahmen \(SEH\) werden nicht mehr abgefangen|  
|C4574 \(Ebene 4\)|'identifier' wird als '0' definiert: beabsichtigten Sie, den '\#if identifier' zu verwenden?|  
|C4608 \(Ebene 3\)|'symbol1' wurde bereits von einem anderen Union\-Member in der Initialisierungsliste initialisiert, 'symbol2'|  
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) \(Ebene 3\)|\#pragma\-Warnung: Keine Warnungsnummer 'number' vorhanden|  
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) \(Ebene 4\)|'Abgeleitete Klasse': Der Standardkonstruktor konnte nicht generiert werden, da auf einen Basisklassen\-Standardkonstruktor nicht zugegriffen werden kann|  
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) \(Ebene 4\)|'Abgeleitete Klasse': Der Kopierkonstruktor konnte nicht generiert werden, da auf einen Basisklassen\-Kopierkonstruktor nicht zugegriffen werden kann|  
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) \(Ebene 4\)|'Abgeleitete Klasse': Der Zuweisungsoperator konnte nicht generiert werden, da auf einen Basisklassen\-Zuweisungsoperator nicht zugegriffen werden kann|  
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) \(Ebene 1\)|'digraphs' werden mit '\-Ze' nicht unterstützt.  Die Zeichensequenz 'Digraph' wird nicht als alternativer Token für 'Zeichen' interpretiert.|  
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) \(Ebene 3\)|'Instanz': Erstellen eines lokalen static\-Objekts ist nicht threadsicher|  
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) \(Ebene 4\)|'Symbol' ist nicht als ein Präprozessormakro definiert, wird durch '0' für 'Direktiven' ersetzt|  
|C4682 \(Ebene 4\)|'Symbol' : es wurde kein direktionales Parameterattribut angegeben, Standardwert \[in\]|  
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) \(Ebene 3\)|'benutzerdefinierter Typ': mögliche Verhaltensänderung, Änderung in der UDT gibt Aufrufkonvention zurück|  
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) \(Ebene 1\)|'Funktion': Die Signatur des nicht privaten Members enthält den privaten systemeigenen Assemblytyp 'systemeigener\_Typ'|  
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) \(Ebene 4\)|'Funktion': Funktion ist nicht inline|  
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) \(Ebene 3\)|Das 32\-Bit\-Gleitkommaergebnis wird im Speicher gespeichert. Möglicherweise kommt es zu einem Leistungsverlust|  
|C4767 \(Ebene 4\)|Der Bereichsname 'symbol' ist länger als 8 Zeichen und wird vom Linker abgeschnitten|  
|C4786 \(Ebene 3\)|'symbol' : Objektname wurde auf 'number'\-Zeichen in den Debuginformationen gekürzt|  
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) \(Ebene 4\)|'Bytes' Bytes Abstand nach dem Konstrukt 'member\_name'|  
|[C4826](../error-messages/compiler-warnings/compiler-warning-level-2-c4826.md) \(Ebene 2\)|Die Konvertierung von 'type1' in 'type2' ist signaturerweitert.  Dies kann zu unerwartetem Laufzeitverhalten führen|  
|[C4837](../error-messages/compiler-warnings/compiler-warning-level-4-c4837.md) \(Ebene 4\)|Es wurde ein Trigraph gefunden: '??%c' wurde durch '%c' ersetzt.|  
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) \(Ebene 1\)|**Breites Zeichenfolgenliteral umgewandelt zu "** <br /> ***LPSTR* "**|  
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) \(Ebene 1\)|**Zeichenfolgenliteral umgewandelt zu "** <br /> ***LPWSTR* "**|  
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) \(Ebene 1\)|'Deklarator': Eine GUID kann nur mit einer Klasse, einer Schnittstelle oder einem Namespace verbunden werden|  
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) \(Ebene 1\)|Unzulässige Kopierinitialisierung. Mehrere benutzerdefinierte Konvertierungen wurden implizit übernommen|  
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) \(Ebene 4\)|Es wird angenommen, dass die Typbibliothek für Anzahl\-Bit\-Pointer erstellt wurde|  
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) \(Ebene 1\)|reinterpret\_cast wird zwischen verknüpften Klassen verwendet: 'Klasse1' und 'Klasse2'|  
|C4962|'Funktion': Profilgesteuerte Optimierungen wurden deaktiviert, da durch die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde|  
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) \(Ebene 4\)|'Symbol': Ausnahmespezifikation stimmt mit der vorherigen Deklaration nicht überein|  
|C4987 \(Ebene 4\)|Es wurde eine nicht standardmäßige Erweiterung verwendet: 'throw \(...\)'|  
|C4988 \(Ebene 4\)|'Symbol': Variable, die außerhalb des Bereichs Klasse\/Funktion deklariert wurde|  
  
## Siehe auch  
 [warning](../preprocessor/warning.md)