---
title: Compilerfehler C2300 bis C2399
ms.date: 04/21/2019
f1_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
helpviewer_keywords:
- C2303
- C2304
- C2305
- C2306
- C2314
- C2321
- C2323
- C2328
- C2329
- C2330
- C2331
- C2335
- C2336
- C2339
- C2340
- C2342
- C2343
- C2347
- C2354
- C2358
- C2359
- C2363
- C2366
- C2367
- C2398
- C2399
ms.assetid: 07ca45b5-b2f0-4049-837b-40a7a3caed88
ms.openlocfilehash: 28ab73857b46fed29e2ba8d7bc051ffb81b54bb3
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857370"
---
# <a name="compiler-errors-c2300-through-c2399"></a>Compilerfehler C2300 bis C2399

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C2300](compiler-error-c2300.md)|"*Klasse*": Klasse weist keinen Destruktor namens ' ~*Klasse*"|
|[Compilerfehler C2301](compiler-error-c2301.md)|Links von "-> ~*Bezeichner*" muss auf Klasse/Struktur/Union zeigen|
|[Compilerfehler C2302](compiler-error-c2302.md)|Links von '. ~*Bezeichner*"müssen die Klasse/Struktur/Union-Typ|
|Compilerfehler C2303|Strukturierte Ausnahmebehandlung kann nicht in einer Coroutine verwendet werden|
|Compilerfehler dass C2304|"*Schlüsselwort*' kann nicht innerhalb eines Catch-Blocks verwendet werden|
|Compilerfehler C2305|"*Datei*" enthält keine Debuginformationen für dieses Modul|
|Compilerfehler C2306|"*Datei*" enthält nicht die aktuelle Debuginformationen für dieses Modul|
|[Compilerfehler C2307](compiler-error-c2307.md)|Pragma *Richtlinie* außerhalb der Funktion verschoben werden müssen, wenn die inkrementelle Kompilierung aktiviert ist|
|[Compilerfehler C2308](compiler-error-c2308.md)|nicht übereinstimmende Zeichenfolgen verketten|
|[Compilerfehler C2309 generiert](compiler-error-c2309.md)|Catch-Handler erwartet eine Ausnahmedeklaration|
|[Compilerfehler C2310 generiert](compiler-error-c2310.md)|Catch-Handler müssen einen Typ angeben.|
|[Compilerfehler C2311 generiert](compiler-error-c2311.md)|"*Typ*": wurde aufgefangen durch "..." in Zeile *Anzahl*|
|[Compilerfehler C2312](compiler-error-c2312.md)|"*type1*": wurde aufgefangen durch "*Typ2*" in Zeile *Anzahl*|
|[Compilerfehler C2313](compiler-error-c2313.md)|"*type1*": wurde aufgefangen durch Verweis ("*Typ2*") in Zeile *Anzahl*|
|Compilerfehler C2314|Schlüsselwort "*Schlüsselwort1*" ist veraltet: Verwenden Sie '*Schlüsselwort2*"stattdessen|
|[Compilerfehler C2315](compiler-error-c2315.md)|"*type1*': Verweis wurde aufgefangen durch"*Typ2*"in Zeile *Anzahl*|
|[Compilerfehler C2316](compiler-error-c2316.md)|"*Typ*": kann nicht abgefangen werden, da Destruktor und/oder Kopierkonstruktor nicht zugegriffen werden kann oder gelöscht werden|
|[Compilerfehler C2317](compiler-error-c2317.md)|"try"-Block ab Zeile '*Anzahl*' besitzt keine Catch-Handler|
|[Compilerfehler C2318](compiler-error-c2318.md)|Kein try-Block mit diesem catch-Handler verbunden|
|[Compilerfehler C2319](compiler-error-c2319.md)|Auf 'try/catch' muss eine zusammengesetzte Anweisung folgen. '{' fehlt|
|[Compilerfehler C2320](compiler-error-c2320.md)|erwartet ':' Zugriffsspezifizierer folgen "*Spezifizierer*"|
|Compilerfehler C2321|"*Bezeichner*" ist ein Schlüsselwort aus, und kann nicht in diesem Kontext nicht verwendet werden|
|[Compilerfehler C2322](compiler-error-c2322.md)|"*Bezeichner*": Adresse von Dllimport '*Bezeichner*' ist nicht statisch|
|Compilerfehler C2323|"*Bezeichner*': nicht-memberoperators oder Delete-Funktionen dürfen nicht deklariert, statisch oder in einem anderen Namespace als dem globalen Namespace|
|[Compilerfehler C2324 generiert](compiler-error-c2324.md)|'*Bezeichner*': Unerwartetes rechts neben ":: ~'|
|[Compilerfehler C2325 generiert](compiler-error-c2325.md)|"*type1*': unerwarteten Typ auf der rechten Seite des" -> ~': erwartet "*Typ2*"|
|[Compilerfehler C2326](compiler-error-c2326.md)|"*Deklarator*': Funktion kann nicht zugegriffen werden kann '*Bezeichner*"|
|[Compilerfehler Fehler C2327](compiler-error-c2327.md)|"*Bezeichner*": ist kein, ein Typname, Static oder Enumerator|
|Compilerfehler C2328|"*Schlüsselwort*": Schlüsselwort wird noch nicht unterstützt.|
|Compilerfehler C2329|"*Bezeichner*": __ptr64 ist nicht verfügbar für Zeiger auf Funktionen|
|Compilerfehler C2330|"Implementation_key ()" ist nur gültig, in einem Bereich von #pragma Start_map_region/stop_map_region eingeschlossen ist|
|Compilerfehler C2331|der Zugriff auf "*Bezeichner*"nun definiert"*accessibility1*", es wurde zuvor definiert, um"*accessibility2*"|
|[Compilerfehler C2332](compiler-error-c2332.md)|"*Typedef*": Fehlender Tagname|
|[Compilerfehler C2333 generiert](compiler-error-c2333.md)|"*Funktion*": Fehler in Funktionsdeklaration; Funktionstext wird übersprungen|
|[Compilerfehler C2334 generiert](compiler-error-c2334.md)|Unerwartete(s) Token vor "*token*"; sichtbarer Funktionstext wird übersprungen|
|Compilerfehler C2335|"*Bezeichner*": ein Typ kann nicht in der Parameterliste einer Funktion eingeführt werden|
|Compilerfehler C2336|"*Typ*": Unzulässiger Typ|
|[Compilerfehler C2337](compiler-error-c2337.md)|"*Attribut*": Attribut wurde nicht gefunden.|
|[Compilerfehler C2338](compiler-error-c2338.md)|*(Fehlermeldung über einen externen Anbieter)*|
|Compilerfehler C2339|"*Bezeichner*": Unzulässiger Typ in eingebetteter IDL|
|Compilerfehler C2340|"*Bezeichner*": "static" kann nur innerhalb einer Klassendefinition verwendet werden|
|[Compilerfehler C2341 generiert](compiler-error-c2341.md)|"*Abschnitt*': Segment muss definiert werden, verwenden #pragma Data_seg, Code_seg oder im vorherigen Abschnitt verwenden|
|Compilerfehler C2342|Syntaxfehler: Typqualifizierer stehen in Konflikt|
|Compilerfehler C2343|"*Abschnitt*": Abschnittsattribute|
|[Compilerfehler C2344](compiler-error-c2344.md)|align (*Anzahl*): Ausrichtung muss eine Potenz von zwei sein|
|[Compilerfehler C2345](compiler-error-c2345.md)|align (*Anzahl*): Ungültiger Ausrichtungswert|
|[Compilerfehler C2346 generiert](compiler-error-c2346.md)|"*Funktion*' kann nicht als systemeigene kompiliert werden:"*Erklärung*"|
|Compilerfehler C2347|Veraltet.|
|[Compilerfehler C2348 generiert](compiler-error-c2348.md)|"*Typ*": ist kein Aggregat im C-Stil, kann nicht in eingebetteter IDL exportiert werden|
|[Compilerfehler C2349](compiler-error-c2349.md)|"*Funktion*' kann nicht als verwaltet kompiliert werden:"*Erklärung*'; verwenden Sie #pragma unmanaged|
|[Compilerfehler C2350](compiler-error-c2350.md)|"*Bezeichner*' ist kein statischer Member|
|[Compilerfehler C2351](compiler-error-c2351.md)|Veraltete Syntax von C++-Konstruktor Initialisierung|
|[Compilerfehler C2352](compiler-error-c2352.md)|"*Bezeichner*": Unzulässiger Aufruf einer nicht statischen Memberfunktion|
|[Compilerfehler C2353 generiert](compiler-error-c2353.md)|Ausnahmespezifikation ist nicht zulässig.|
|Compilerfehler C2354 generiert|Veraltet.|
|[Compilerfehler C2355](compiler-error-c2355.md)|"this": kann nur innerhalb nicht statischer Memberfunktionen oder nicht statische datenmemberinitialisierer verwiesen werden|
|[Compilerfehler C2356 generiert](compiler-error-c2356.md)|Initialisierungssegment darf während der Übersetzungseinheit nicht geändert.|
|[Compilerfehler C2357 generiert](compiler-error-c2357.md)|"*Bezeichner*": muss eine Funktion vom Typ "*Typ*"|
|Compilerfehler C2358|"*Bezeichner*': eine statische Eigenschaft kann nicht außerhalb einer Klassendefinition definiert werden|
|Compilerfehler C2359|Veraltet.|
|[Compilerfehler C2360 generiert](compiler-error-c2360.md)|Initialisierung von "*Bezeichner*" wird von "Case"-Bezeichnung übersprungen|
|[Compilerfehler C2361 generiert](compiler-error-c2361.md)|Initialisierung von "*Bezeichner*" durch "Default"-Bezeichnung übersprungen|
|[Compilerfehler C2362](compiler-error-c2362.md)|Initialisierung von "*Bezeichner*" wird übersprungen, indem Sie ' Gehe zu *Bezeichnung*"|
|Compilerfehler C2363|vom Compiler die inhärente numerische Limit-Funktion erfordert ein Zeichenfolgenliteral-argument|
|[Compilerfehler C2364 generiert](compiler-error-c2364.md)|"*Typ*": Unzulässiger Typ für das benutzerdefinierte Attribut|
|[Compilerfehler C2365](compiler-error-c2365.md)|"*member1*": Neudefinition; vorherige Definition war "*member2*"|
|Compilerfehler C2366|"*Bezeichner*": Neudefinition; unterschiedlicher Implementation_key-Spezifizierer|
|Compilerfehler C2367|Veraltet.|
|[Compilerfehler C2368](compiler-error-c2368.md)|"*Bezeichner*": Neudefinition; unterschiedliche Allocation-Spezifizierer|
|[Compilerfehler C2369](compiler-error-c2369.md)|"*Bezeichner*": Neudefinition; unterschiedliche Feldindizes|
|[Compilerfehler C2370](compiler-error-c2370.md)|"*Bezeichner*": Neudefinition; unterschiedliche Speicherklassen|
|[Compilerfehler C2371 generiert](compiler-error-c2371.md)|"*Bezeichner*": Neudefinition; unterschiedliche Basistypen|
|[Compilerfehler C2372](compiler-error-c2372.md)|"*Bezeichner*": Neudefinition; unterschiedliche Dereferenzierungstypen|
|[Compilerfehler C2373](compiler-error-c2373.md)|"*Bezeichner*": Neudefinition; unterschiedliche Typmodifizierer|
|[Compilerfehler C2374](compiler-error-c2374.md)|"*Bezeichner*": Neudefinition; mehrfachinitialisierung|
|[Compilerfehler C2375](compiler-error-c2375.md)|"*Bezeichner*": Neudefinition; unterschiedliche Bindung|
|[Compilerfehler C2376](compiler-error-c2376.md)|"*Bezeichner*": Neudefinition; unterschiedliche segmentspeicherbelegung|
|[Compilerfehler C2377](compiler-error-c2377.md)|"*Bezeichner*": Neudefinition; Typedef kann nicht mit einem anderen Symbol überladen werden|
|[Compilerfehler C2378](compiler-error-c2378.md)|"*Bezeichner*": Neudefinition; Symbol kann nicht mit Typedef überladen werden|
|[Compilerfehler C2379 generiert](compiler-error-c2379.md)|formaler Parameter *Anzahl* hat einen anderen Typ, wenn die höher gestuft|
|[Compilerfehler C2380](compiler-error-c2380.md)|Typ(en) vor "*Bezeichner*"-Konstruktor mit Ergebnistyp oder unzulässige Neudefinition eines Klassennamens?|
|[Compilerfehler C2381 generiert](compiler-error-c2381.md)|"*Bezeichner*": Neudefinition; "__declspec(noreturn)" oder "[[Noreturn]]" unterschiedlich|
|[Compilerfehler C2382](compiler-error-c2382.md)|"*Bezeichner*": Neudefinition; unterschiedliche Ausnahmespezifikationen|
|[Compilerfehler C2383](compiler-error-c2383.md)|"*Bezeichner*': Standardargumente dürfen nicht auf dieses Symbol|
|[Compilerfehler C2384](compiler-error-c2384.md)|"*Member*": Thread_local oder __declspec(thread) kann nicht auf einen Member einer verwalteten/WinRT-Klasse angewendet|
|[Compilerfehler C2385](compiler-error-c2385.md)|Mehrdeutiger Zugriff von "*Member*"|
|[Compilerfehler C2386](compiler-error-c2386.md)|"*Bezeichner*": ein Symbol mit diesem Namen ist im aktuellen Bereich bereits vorhanden.|
|[Compilerfehler C2387 generiert](compiler-error-c2387.md)|"*Bezeichner*": mehrdeutige Basisklasse|
|[Compilerfehler C2388](compiler-error-c2388.md)|"*Bezeichner*": ein Symbol kann nicht mit __declspec(appdomain) und __declspec(process) gleichzeitig deklariert werden|
|[Compilerfehler C2389](compiler-error-c2389.md)|"*Operator*': Ungültiger Nullptr-Operand.|
|[Compilerfehler C2390 generiert](compiler-error-c2390.md)|"*Bezeichner*': eine inkorrekte Speicherklasse*Spezifizierer*"|
|[Compilerfehler C2391](compiler-error-c2391.md)|"*Bezeichner*": "Friend" kann nicht verwendet werden, während der Typdefinition|
|[Compilerfehler C2392](compiler-error-c2392.md)|"*member1*": Covariant-Typen sind nicht andernfalls verwaltet/WinRT-Typen unterstützt "*member2*" überschrieben werden|
|[Compilerfehler C2393 generiert](compiler-error-c2393.md)|"*Symbol*': anwendungsdomänenspezifisches Symbol kann nicht in Segment zugeordnet werden kann '*Segment*"|
|[Compilerfehler C2394](compiler-error-c2394.md)|"*Typ*:: Operator *Operator*": CLR/WinRT-Operator ist ungültig. Mindestens ein Parameter muss die folgenden Typen aufweisen:  "T ^', ' t ^ %', ' t ^ &', wobei T = '*Typ*"|
|[Compilerfehler C2395](compiler-error-c2395.md)|"*Typ*:: Operator *Operator*": CLR/WinRT-Operator ist ungültig. Mindestens ein Parameter muss die folgenden Typen aufweisen: "T ', ' t %', ' t &', ' t ^', ' t ^ %", ' t ^ & ", wobei T ="*Typ*"|
|[Compilerfehler C2396](compiler-error-c2396.md)|"*type1*:: Operator *Typ2*": CLR/WinRT eine benutzerdefinierte Konvertierungsfunktion ist ungültig. Muss die Konvertierung von oder in konvertieren: "T ^', ' t ^ %', ' t ^ &', wobei T = '*type1*"|
|[Compilerfehler C2397](compiler-error-c2397.md)|Konvertierung von '*type1*'to'*Typ2*"erfordert eine einschränkende Konvertierung|
|Compilerfehler C2398|Element "*Anzahl*': Konvertierung von '*type1*'to'*Typ2*" erfordert eine einschränkende Konvertierung|
|Compilerfehler C2399|Veraltet.|

## <a name="see-also"></a>Siehe auch

[C /C++ Compiler- und Build tools, Fehler und Warnungen](../compiler-errors-1/c-cpp-build-errors.md) \
[Compilerfehler C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
