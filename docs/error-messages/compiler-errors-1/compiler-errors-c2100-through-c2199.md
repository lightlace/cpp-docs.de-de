---
title: Compilerfehlers C2100 through C2199 | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2131
- C2136
- C2176
- C2187
- C2189
helpviewer_keywords:
- C2119
- C2123
- C2125
- C2126
- C2127
- C2131
- C2136
- C2176
- C2187
- C2189
dev_langs:
- C++
ms.assetid: 1ccab076-0954-4386-b959-d3112a6793ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f276776028fde88e4ef1e4559f0dd4db08abfe03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-errors-c2100-through-c2199"></a>Compilerfehlers C2100 through C2199

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C2100](compiler-error-c2100.md)|ungültige Dereferenzierung.|
|[Compilerfehler C2101](compiler-error-c2101.md)|"&" auf Konstante|
|[Compilerfehler C2102](compiler-error-c2102.md)|"&" erfordert I-Wert|
|[Compilerfehler C2103](compiler-error-c2103.md)|'&' auf Registervariable|
|[Compilerfehler C2104](compiler-error-c2104.md)|"&" auf Bitfeld ignoriert|
|[Compilerfehler C2105](compiler-error-c2105.md)|"*Operator*' benötigt l-Wert|
|[Compilerfehler C2106](compiler-error-c2106.md)|"*Operator*": linke Operand muss ein l-Wert|
|[Compilerfehler C2107](compiler-error-c2107.md)|Ungültiger Index, Dereferenzierung nicht erlaubt|
|[Compilerfehler C2108](compiler-error-c2108.md)|Index ist kein Ganzzahltyp|
|[Compilerfehler C2109](compiler-error-c2109.md)|tiefgestellte Array oder Zeiger-Operanden erfordert|
|[Compilerfehler C2110](compiler-error-c2110.md)|"+": zwei Zeiger kann nicht hinzugefügt werden.|
|[Compilerfehler C2111](compiler-error-c2111.md)|"+": Zeigeraddition erfordert einen Ganzzahloperanden|
|[Compilerfehler C2112](compiler-error-c2112.md)|'-': Zeiger-Subtraktion erfordert einen Ganzzahl- oder Zeigertyp Ganzzahloperanden|
|[Compilerfehler C2113](compiler-error-c2113.md)|'-': Zeiger kann nur von einem anderen Zeiger subtrahiert werden|
|[Compilerfehler C2114](compiler-error-c2114.md)|"*Operator*': Zeiger auf der linken Seite; erfordert Ganzzahl auf rechts|
|[Compilerfehler C2115](compiler-error-c2115.md)|"*Operator*": Inkompatible Typen|
|[Compilerfehler C2116](compiler-error-c2116.md)|Unterschiedliche Funktionsparameterlisten|
|[Compilerfehler C2117](compiler-error-c2117.md)|"*Bezeichner*": Arraygrenze überschritten|
|[Compilerfehler C2118](compiler-error-c2118.md)|Negativer Index|
|Compilerfehler Fehler C2119|"*Bezeichner*": der Typ für '*Typ*"kann nicht aus einer leeren Initialisierer abgeleitet werden|
|[Compilerfehler C2120](compiler-error-c2120.md)|mit allen Arten 'void' ungültig|
|[Compilerfehler C2121](compiler-error-c2121.md)|'#': Ungültiges Zeichen: möglicherweise das Ergebnis der makroerweiterung eines|
|[Compilerfehler C2122](compiler-error-c2122.md)|"*Bezeichner*': Parameter des Prototyps in der Liste ist ungültig|
|Compilerfehler Fehler C2123|"*Bezeichner*": Alias-Vorlagen können nicht explizit oder teilweise spezialisiert werden|
|[Compilerfehler C2124](compiler-error-c2124.md)|Division oder Modulo durch Null|
|Compilerfehler Fehler C2125|"Constexpr" ist nicht kompatibel mit "*token*"|
|Compilerfehler Fehler C2126|"*Bezeichner*" kann nicht mit "Constexpr" Spezifizierer deklariert werden|
|Compilerfehler Fehler C2127|"*Bezeichner*': Unzulässiger Initialisierung von"Constexpr"-Entität mit einem nicht konstanten Ausdruck|
|[Compilerfehler C2128](compiler-error-c2128.md)|"*Funktion*": Alloc_text/Same_seg gilt nur für Funktionen mit C-Bindung|
|[Compilerfehler C2129](compiler-error-c2129.md)|statische Funktion "*Bezeichner*' deklariert, aber nicht definiert.|
|[Compilerfehler C2130](compiler-error-c2130.md)|#line erwartet eine Zeichenfolge mit dem Dateinamen, gefunden "*token*"|
|Compilerfehler Fehler C2131|der Ausdruck nicht auf eine Konstante ausgewertet.|
|[Compilerfehler C2132](compiler-error-c2132.md)|Syntaxfehler: Bezeichner nicht erwartet|
|[Compilerfehler C2133](compiler-error-c2133.md)|"*Bezeichner*": Unbekannte Größe|
|[Compilerfehler C2134](compiler-error-c2134.md)|"*Funktion*": Aufruf führt nicht zu einem konstanten Ausdruck|
|[Compilerfehler C2135](compiler-error-c2135.md)|"*Operator*": Ungültiger bitfeldvorgang|
|Compilerfehler Fehler C2136|Erstellen von API-Vertrag nicht zulässig|
|[Compilerfehler C2137](compiler-error-c2137.md)|leere Zeichenkonstante|
|[Compilerfehler C2138](compiler-error-c2138.md)|definieren eine Enumeration ohne Mitglieder nicht zulässig|
|[Compilerfehler C2139](compiler-error-c2139.md)|"*Klasse*': eine nicht definierte Klasse ist nicht zulässig, als Argument für das systeminterne Typmerkmal Compiler"*Merkmals*"|
|[Compilerfehler C2140](compiler-error-c2140.md)|"*Typ*": ein Typ, der einen generischen Typparameter abhängig ist, darf nicht als Argument für das systeminterne Typmerkmal Compiler "*Merkmals*"|
|[Compilerfehler C2141](compiler-error-c2141.md)|Überlauf der Array-Größe|
|[Compilerfehler C2142](compiler-error-c2142.md)|unterschiedliche Funktionsdeklarationen, die Variable nur in einem von ihnen angegebenen Parameter|
|[Compilerfehler C2143](compiler-error-c2143.md)|Syntaxfehler: Fehlendes '*ttoken1*'before'*token2*"|
|[Compilerfehler C2144](compiler-error-c2144.md)|Syntaxfehler: "*Typ*"sollte vorangestellt werden"*token2*"|
|[Compilerfehler C2145](compiler-error-c2145.md)|Syntaxfehler: Fehlendes '*token*"vor Bezeichner|
|[Compilerfehler C2146](compiler-error-c2146.md)|Syntaxfehler: Fehlendes '*token*"vor Bezeichner"*Bezeichner*"|
|[Compilerfehler C2147](compiler-error-c2147.md)|Syntaxfehler: "*token*" ist ein neues Schlüsselwort|
|[Compilerfehler C2148](compiler-error-c2148.md)|Gesamtgröße des Arrays darf nicht 0 X*Wert* Bytes|
|[Compilerfehler C2149](compiler-error-c2149.md)|"*Bezeichner*': benannte Bitfelder dürfen keine NULL Breite haben|
|[Compilerfehler C2150](compiler-error-c2150.md)|"*Bezeichner*": Bitfelder muss vom Typ 'Int','signed Int' oder 'unsigned Int' haben.|
|[Compilerfehler C2151](compiler-error-c2151.md)|mehrere Language-Attribut|
|[Compilerfehler C2152](compiler-error-c2152.md)|"*Bezeichner*': Zeiger auf Funktionen mit verschiedenen Attributen|
|[Compilerfehler C2153](compiler-error-c2153.md)|Integer-Literale müssen mindestens eine Ziffer enthalten.|
|[Compilerfehler C2154](compiler-error-c2154.md)|"*Typ*': nur Enumerationstyp ist zulässig, als Argument für das systeminterne Typmerkmal Compiler"*Merkmal ""*"|
|[Compilerfehler C2155](compiler-error-c2155.md)|'?': Ungültiges linkes erwartet Operanden arithmetische oder Zeiger vom Typ|
|[Compilerfehler C2156](compiler-error-c2156.md)|Pragma muss außerhalb der Funktion liegen|
|[Compilerfehler C2157](compiler-error-c2157.md)|"*Bezeichner*': muss vor der Verwendung in der Pragma-Liste deklariert werden|
|[Compilerfehler C2158](compiler-error-c2158.md)|"*Typ*": #pragma Make_public-Direktive wird derzeit für systemeigene Nichtvorlagentypen nur unterstützt|
|[Compilerfehler C2159](compiler-error-c2159.md)|Mehr als eine Speicherklasse angegeben|
|[Compilerfehler C2160](compiler-error-c2160.md)|"##" kann nicht am Anfang einer Makrodefinition stehen|
|[Compilerfehler C2161](compiler-error-c2161.md)|"##" kann nicht am Ende einer Makrodefinition stehen|
|[Compilerfehler C2162](compiler-error-c2162.md)|formaler Makroparameter erwartet|
|[Compilerfehler C2163](compiler-error-c2163.md)|"*Funktion*': nicht als systeminterne Funktion verfügbar|
|[Compilerfehler C2164](compiler-error-c2164.md)|"*Funktion*": systeminterne Funktion nicht deklariert|
|[Compilerfehler C2165](compiler-error-c2165.md)|"*Modifizierer*': Zeiger auf Daten kann nicht geändert werden.|
|[Compilerfehler C2166](compiler-error-c2166.md)|L-Wert gibt ein const-Objekt an|
|[Compilerfehler C2167](compiler-error-c2167.md)|"*Funktion*': zu viele aktuelle Parameter für die systeminterne Funktion|
|[Compilerfehler C2168](compiler-error-c2168.md)|"*Funktion*': zu wenig Parameter an systeminterne Funktion|
|[Compilerfehler C2169](compiler-error-c2169.md)|"*Funktion*": systeminterne Funktion kann nicht definiert werden|
|[Compilerfehler C2170](compiler-error-c2170.md)|"*Bezeichner*': nicht als Funktion deklariert, kann nicht systemintern sein|
|[Compilerfehler C2171](compiler-error-c2171.md)|"*Operator*': Unzulässiger für Operanden vom Typ"*Typ*"|
|[Compilerfehler C2172](compiler-error-c2172.md)|"*Funktion*": übergebener Parameter ist kein Zeiger: Parameter *Anzahl*|
|[Compilerfehler C2173](compiler-error-c2173.md)|"*Funktion*": übergebener Parameter ist kein Zeiger: Parameter *Anzahl*, Parameterliste *Anzahl*|
|[Compilerfehler C2174](compiler-error-c2174.md)|"*Funktion*': Parameter hat den Typ 'Void': Parameter *Anzahl*, Parameterliste *Anzahl*|
|[Compilerfehler C2175](compiler-error-c2175.md)|"*Gebietsschema*': Ungültiges Gebietsschema|
|Compilerfehler Fehler C2176|eine return-Anweisung kann nicht in der Handler eine Funktion-Try-Block zugeordnet einen Konstruktor angezeigt werden.|
|[Compilerfehler C2177](compiler-error-c2177.md)|Konstante zu groß|
|[Compilerfehler C2178](compiler-error-c2178.md)|"*Bezeichner*"kann nicht mit deklariert werden"*Spezifizierer*' Spezifizierer|
|[Compilerfehler C2179](compiler-error-c2179.md)|"*Typ*": Ein Attributargument kann keine Typparameter verwenden|
|[Compilerfehler C2180](compiler-error-c2180.md)|steuernder Ausdruck weist den Typ "*Typ*"|
|[Compilerfehler C2181](compiler-error-c2181.md)|Ungültiges "else" ohne zugehöriges "if"|
|[Compilerfehler C2182](compiler-error-c2182.md)|"*Bezeichner*': Unzulässige Verwendung des Typs 'Void'|
|[Compilerfehler C2183](compiler-error-c2183.md)|Syntaxfehler: Übersetzungseinheit ist leer|
|[Compilerfehler C2184](compiler-error-c2184.md)|"*Typ*": Ungültiger Typ für __except-Ausdruck|
|[Compilerfehler C2185](compiler-error-c2185.md)|"*Bezeichner*': Unzulässiger-Reservierung|
|[Compilerfehler C2186](compiler-error-c2186.md)|"*Operator*": Ungültiger Operand vom Typ "Void"|
|Compilerfehler Fehler C2187|Syntaxfehler: "*token*" wurde unerwartet hier|
|[Compilerfehler C2188](compiler-error-c2188.md)|"*Anzahl*': zu groß für Breitzeichen|
|Compilerfehler Fehler C2189|"Alignas"-Attribut kann nicht auf ein Bitfeld, einen Funktionsparameter, einer Ausnahmedeklaration angewendet werden, oder eine Variable deklariert, mit "Speicherklasse registrieren"|
|[Compilerfehler C2190](compiler-error-c2190.md)|erste Parameterliste länger als zweite|
|[Compilerfehler C2191](compiler-error-c2191.md)|zweite Parameterliste länger als erste|
|[Compilerfehler C2192](compiler-error-c2192.md)|Parameter "*Anzahl*" andere Deklaration|
|[Compilerfehler C2193](compiler-error-c2193.md)|"*Bezeichner*': bereits in einem Segment|
|[Compilerfehler C2194](compiler-error-c2194.md)|"*Bezeichner*": ist ein Textsegment|
|[Compilerfehler C2195](compiler-error-c2195.md)|"*Bezeichner*": ist ein Datensegment|
|[Compilerfehler C2196](compiler-error-c2196.md)|Case-Wert "*Wert*" bereits verwendet.|
|[Compilerfehler C2197](compiler-error-c2197.md)|"*Funktion*': zu viele Argumente für Aufruf|
|[Compilerfehler C2198](compiler-error-c2198.md)|"*Funktion*': zu wenige Argumente für Aufruf|
|[Compilerfehler C2199](compiler-error-c2199.md)|Syntaxfehler: gefunden '*Bezeichner* ("im globalen Gültigkeitsbereich (war eine Deklaration beabsichtigt?)|  