---
title: Compilerfehler C3000 bis C3099 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
helpviewer_keywords:
- C3051
- C3061
- C3064
- C3067
- C3074
- C3078
- C3079
- C3081
- C3082
- C3086
- C3088
- C3089
- C3090
- C3091
- C3092
- C3093
- C3098
dev_langs:
- C++
ms.assetid: 01b7b9cb-b351-4b5a-8cb0-1fcddb08d2ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7565a2656bcb5c9ad10c83179b563423d42be7b5
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44319044"
---
# <a name="compiler-errors-c3000-through-c3099"></a>Compilerfehler C3000 bis C3099

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|Compilerfehler Fehler C3000|Veraltet.|
|[Compilerfehler C3001](compiler-error-c3001.md)|"*Nachricht*": wurde ein OpenMP-Direktivenname erwartet|
|[Compilerfehler C3002](compiler-error-c3002.md)|"*name1* *name2*": mehrere OpenMP-Direktivennamen|
|[Compilerfehler C3003](compiler-error-c3003.md)|"*Richtlinie*": OpenMP-Direktivenname nach Direktivenklauseln nicht zulässig.|
|[Compilerfehler C3004](compiler-error-c3004.md)|"*Klausel*": ungültig OpenMP-Klausel '*Richtlinie*"Richtlinie|
|[Compilerfehler C3005](compiler-error-c3005.md)|"*Nachricht*': Unerwartetes Token gefunden in OpenMP"*Richtlinie*"Richtlinie|
|[Compilerfehler C3006](compiler-error-c3006.md)|"*Klausel*':-Klausel für OpenMP"*Richtlinie*"-Direktive fehlt ein erwartetes Argument|
|[Compilerfehler C3007](compiler-error-c3007.md)|"*Klausel*": OpenMP-Klausel '*Richtlinie*' Direktive nimmt kein Argument|
|[Compilerfehler C3008](compiler-error-c3008.md)|"*Argument*': Argument fehlt eine schließende") "OpenMP"*Richtlinie*"Richtlinie|
|[Compilerfehler C3009](compiler-error-c3009.md)|"*Bezeichnung*': Einsprung in strukturierten Block von OpenMP nicht zulässig|
|[Compilerfehler C3010](compiler-error-c3010.md)|"*Bezeichnung*': Aussprung aus strukturiertem Block von OpenMP nicht zulässig|
|[Compilerfehler C3011](compiler-error-c3011.md)|Eine Inlineassembly direkt innerhalb eines parallelen Bereichs ist nicht zulässig.|
|[Compilerfehler C3012](compiler-error-c3012.md)|"*Funktion*": systeminterne Funktion direkt innerhalb eines parallelen Bereichs ist nicht zulässig|
|[Compilerfehler C3013](compiler-error-c3013.md)|"*Klausel*': Klausel darf nur einmal in OpenMP"*Richtlinie*"Richtlinie|
|[Compilerfehler C3014](compiler-error-c3014.md)|erwartet eine for-Schleife folgt OpenMP "*Richtlinie*" Richtlinie|
|[Compilerfehler C3015](compiler-error-c3015.md)|Die Initialisierung in der For-Anweisung von OpenMP weist eine ungültige Form auf.|
|[Compilerfehler C3016](compiler-error-c3016.md)|"*Bezeichner*": Indexvariable in OpenMP for-Anweisung muss Ganzzahltyps mit Vorzeichen aufweisen|
|[Compilerfehler C3017](compiler-error-c3017.md)|Der Beendigungstest in der For-Anweisung von OpenMP weist eine ungültige Form auf.|
|[Compilerfehler C3018](compiler-error-c3018.md)|"*Bezeichner*": OpenMP 'for' Test oder das Inkrement muss die Indexvariable verwenden '*Variable*"|
|[Compilerfehler C3019](compiler-error-c3019.md)|Das Inkrement in OpenMP der for-Anweisung weist eine ungültige form|
|[Compilerfehler C3020](compiler-error-c3020.md)|"*Variable*": Indexvariable der for-Schleife von OpenMP kann nicht im Schleifenkörper geändert werden|
|[Compilerfehler C3021](compiler-error-c3021.md)|"*Argument*': Argument von OpenMP ist leer"*Richtlinie*"Richtlinie|
|[Compilerfehler C3022](compiler-error-c3022.md)|"*Richtlinie*': Ungültiger Plantyp von"*Richtlinie*'on OpenMP"*Richtlinie*" Richtlinie|
|[Compilerfehler C3023](compiler-error-c3023.md)|"*Argument*": Unerwartetes Token gefunden, die im Argument für die OpenMP "*Richtlinie*"-Klausel|
|[Compilerfehler C3024](compiler-error-c3024.md)|'Schedule(Runtime)":': Chunk_size-Ausdruck ist nicht zulässig.|
|[Compilerfehler C3025](compiler-error-c3025.md)|"*Klausel*": ein ganzzahliger Ausdruck erwartet|
|[Compilerfehler C3026](compiler-error-c3026.md)|"*Klausel*": konstanter Ausdruck muss positiv sein|
|[Compilerfehler C3027](compiler-error-c3027.md)|"*Klausel*': arithmetischer Ausdruck oder Zeigerausdruck erwartet|
|[Compilerfehler C3028](compiler-error-c3028.md)|"*Member*': nur eine Variable oder ein statischer Datenmember kann in einer Datenfreigabeklausel verwendet werden|
|[Compilerfehler C3029](compiler-error-c3029.md)|"*Symbol*": kann nur einmal in der Datenfreigabe-Klauseln in einer OpenMP-Direktive|
|[Compilerfehler C3030](compiler-error-c3030.md)|"*Bezeichner*': Variable '*Richtlinie*'-Klausel/-Direktive kann keinen Verweistyp aufweisen|
|[Compilerfehler C3031](compiler-error-c3031.md)|"*Bezeichner*': Variable in Reduction-Klausel muss arithmetischen Skalartyp aufweisen|
|[Compilerfehler C3032](compiler-error-c3032.md)|"*Bezeichner*': Variable '*Klausel*"Klausel kann keinen unvollständigen Typ"*Typ*"|
|[Compilerfehler C3033](compiler-error-c3033.md)|"*Bezeichner*': Variable '*Klausel*' Klausel kann keinen konstant qualifizierten Typ haben|
|[Compilerfehler C3034](compiler-error-c3034.md)|OpenMP "*Richtlinie*" Richtlinie kann nicht direkt geschachtelt werden in"*Richtlinie*" Richtlinie|
|[Compilerfehler C3035](compiler-error-c3035.md)|Die ordered-Direktive von OpenMP muss mit der ordered-Klausel direkt an eine For-Direktive oder eine Parallel For-Direktive gebunden werden.|
|[Compilerfehler C3036](compiler-error-c3036.md)|"*Klausel*": ungültiges Operatortoken in der "Reduction"-Klausel von OpenMP|
|[Compilerfehler C3037](compiler-error-c3037.md)|"*Bezeichner*': Variable '*Klausel*' Klausel muss im umschließenden Kontext freigegeben werden|
|[Compilerfehler C3038](compiler-error-c3038.md)|"*Bezeichner*': Variable in der private-Klausel kann nicht im umschließenden Kontext keine Reduction-Variable sein|
|[Compilerfehler C3039](compiler-error-c3039.md)|"*Bezeichner*": Indexvariable in OpenMP for-Anweisung handelt es sich nicht um eine Reduction-Variable|
|[Compilerfehler C3040](compiler-error-c3040.md)|"*Bezeichner*': Typ der Variable in Reduction-Klausel ist nicht kompatibel mit Reduction-Operator"*Operator*"|
|[Compilerfehler C3041](compiler-error-c3041.md)|"*Bezeichner*': Variable in der Copyprivate-Klausel muss im umschließenden Kontext privat sein|
|[Compilerfehler C3042](compiler-error-c3042.md)|darf nicht 'Copyprivate' und 'Nowait-Klauseln zusammen auf OpenMP "*Richtlinie*" Richtlinie|
|[Compilerfehler C3043](compiler-error-c3043.md)|Die critical-Direktive von OpenMP kann nicht in einer critical-Direktive mit dem gleichen Namen geschachtelt werden.|
|[Compilerfehler C3044](compiler-error-c3044.md)|"Section": nur zulässig, direkter Schachtelung unter einer "Sections"-Direktive von OpenMP|
|[Compilerfehler C3045](compiler-error-c3045.md)|Es wurde erwartet, dass auf die sections-Direktive von OpenMP eine Verbundanweisung folgt. '{' fehlt|
|[Compilerfehler C3046](compiler-error-c3046.md)|Fehlender strukturierter Block in einem #pragma omp sections-Bereich von OpenMP.|
|[Compilerfehler C3047](compiler-error-c3047.md)|Vor einem strukturierten Block in einem sections-Bereich von OpenMP muss sich "#pragma omp section" befinden.|
|[Compilerfehler C3048](compiler-error-c3048.md)|Der Ausdruck, der auf "#pragma omp atomic" folgt, weist eine ungültige Form auf.|
|[Compilerfehler C3049](compiler-error-c3049.md)|"*Argument*": Ungültiges Argument in der 'Default'-Klausel (OpenMP)|
|[Compilerfehler C3050](compiler-error-c3050.md)|"*Klasse*': eine Verweisklasse kann nicht von erben"*Bezeichner*"|
|Compilerfehler Fehler C3051|Veraltet.|
|[Compilerfehler C3052](compiler-error-c3052.md)|"*Bezeichner*': Variable nicht in einer Datenfreigabeklausel unter einer default(None)-Klausel angezeigt.|
|[Compilerfehler C3053](compiler-error-c3053.md)|"*Bezeichner*': 'Threadprivate' ist nur für globale oder statische Datenelemente gültig|
|[Compilerfehler C3054](compiler-error-c3054.md)|"#pragma omp parallel" wird in einer generischen Klasse oder Funktion derzeit nicht unterstützt.|
|[Compilerfehler C3055](compiler-error-c3055.md)|"*Bezeichner*": Symbol kann nicht verwiesen werden, bevor sie in der 'Threadprivate'-Direktive verwendet wird|
|[Compilerfehler C3056](compiler-error-c3056.md)|"*Bezeichner*": Symbol befindet sich nicht im gleichen Bereich wie die 'Threadprivate'-Direktive|
|[Compilerfehler C3057](compiler-error-c3057.md)|"*Bezeichner*": dynamische Initialisierung von 'Threadprivate'-Symbolen wird derzeit nicht unterstützt.|
|[Compilerfehler C3058](compiler-error-c3058.md)|"*Bezeichner*": Symbol, die nicht als "Threadprivate" deklariert werden, bevor sie in der Copyin-Klausel verwendet wird|
|[Compilerfehler C3059](compiler-error-c3059.md)|"*Bezeichner*': 'Threadprivate'-Symbol kann nicht verwendet werden, der '*Klausel*"-Klausel|
|[Compilerfehler C3060](compiler-error-c3060.md)|"*Bezeichner*': eine Friend-Funktion kann nicht mit einem qualifizierten Namen (es kann nur deklariert werden) innerhalb einer Klasse definiert werden|
|Compilerfehler Fehler C3061|Operator '*Operator*': für die Enumeration nicht zulässig "*Typ*"mit der zugrunde liegenden Typ'*Typ*"|
|[Compilerfehler C3062](compiler-error-c3062.md)|"*Bezeichner*': Enumerator ist ein Wert erforderlich, da der zugrunde liegenden Typ ist"*Typ*"|
|[Compilerfehler C3063](compiler-error-c3063.md)|Operator '*Operator*": alle Operanden müssen den gleichen Enumerationstyp aufweisen|
|Compilerfehler Fehler C3064|"*Bezeichner*": muss ein einfacher Typ oder in einem aufgelöst|
|[Compilerfehler C3065](compiler-error-c3065.md)|Die Eigenschaftendeklaration im Nichtklassenbereich ist nicht zulässig.|
|[Compilerfehler C3066](compiler-error-c3066.md)|Es gibt mehrere Möglichkeiten, ein Objekt dieses Typs aufgerufen werden, kann mit diesen Argumenten|
|Compilerfehler Fehler C3067|eine Initialisiererliste kann nicht verwendet werden, mit dem integrierten Operator]|
|[Compilerfehler C3068](compiler-error-c3068.md)|"*Bezeichner*': eine naked-Funktion dürfen nicht Objekten, die Entladung erforderlich wäre, wenn eine C++-Ausnahme aufgetreten ist.|
|[Compilerfehler C3069](compiler-error-c3069.md)|Operator '*Operator*': für den Enumerationstyp nicht zulässig.|
|[Compilerfehler C3070](compiler-error-c3070.md)|"*Bezeichner*": Eigenschaft hat keine'set'-Methode|
|[Compilerfehler C3071](compiler-error-c3071.md)|Operator '*Operator*' kann nur auf eine Instanz einer Verweisklasse oder einen Werttyp angewendet werden|
|[Compilerfehler C3072](compiler-error-c3072.md)|Operator '*Operator*' kann nicht mit einer Instanz eines Ref-Klasse verwenden, die den unären '% s'-Operator, um eine Instanz einer Verweisklasse konvertieren in einen Handletyp Klasse angewendet werden|
|[Compilerfehler C3073](compiler-error-c3073.md)|"*Bezeichner*": Verweisklasse hat keinen benutzerdefinierten Kopierkonstruktor|
|Compilerfehler Fehler C3074|ein Array kann nicht mit einem Initialisierer in Klammern initialisiert werden|
|[Compilerfehler C3075](compiler-error-c3075.md)|"*Bezeichner*': Sie können keine Instanz eines Referenztyps einbetten"*Typ*", in einen Werttyp|
|[Compilerfehler C3076](compiler-error-c3076.md)|"*Bezeichner*': Sie können keine Instanz eines Referenztyps einbetten"*Typ*", in einem systemeigenen Typ|
|[Compilerfehler C3077](compiler-error-c3077.md)|"*Bezeichner*": ein Finalizer kann nur ein Member eines Verweistyps sein|
|Compilerfehler Fehler C3078|Größe des Arrays muss in neuen Ausdrücken angegeben werden|
|Compilerfehler Fehler C3079|eine Initialisiererliste kann nicht als rechter Operand dieses Zuweisungsoperators verwendet werden|
|[Compilerfehler C3080](compiler-error-c3080.md)|"*Finalizer*": ein Finalizer kann keiner Storage-Class-Specifier aufweisen|
|Compilerfehler Fehler C3081|Veraltet.|
|Compilerfehler C3082|Veraltet.|
|[Compilerfehler C3083](compiler-error-c3083.md)|"*Bezeichner*': das Symbol auf der linken Seite des ein '::' muss ein Typ sein|
|[Compilerfehler C3084](compiler-error-c3084.md)|"*Bezeichner*': nicht möglich, ein Destruktor/Finalizer '*Schlüsselwort*"|
|[Compilerfehler C3085](compiler-error-c3085.md)|"*Bezeichner*": ein Konstruktor kann nicht sein. '*Schlüsselwort*"|
|Compilerfehler Fehler C3086|"Std:: initializer_list" kann nicht gefunden werden: Sie müssen #include \<Initializer_list >|
|[Compilerfehler C3087](compiler-error-c3087.md)|"*Bezeichner*": Aufruf von "*Deklaration*" dieser Member bereits initialisiert|
|Compilerfehler Fehler C3088|"*Klasse*': Der Attributkonstruktor muss benannte formale Argumente aufweisen|
|Compilerfehler Fehler C3089|"*Bezeichner*": Name des Parameters entspricht nicht der Name des Elements, der alle Daten|
|Compilerfehler Fehler C3090|"*Klasse*': Attributklasse handelt es sich nicht um eine Vorlage|
|Compilerfehler Fehler C3091|"*Klasse*": Attribute-Klasse kann keine Basisklassen aufweisen.|
|Compilerfehler Fehler C3092|"*Klasse*": Attribut-Klassenmember kann nicht, ein wenig Feld'static' oder 'const'|
|Compilerfehler Fehler C3093|"*Typ*': Typ ist nicht zulässig, für den Attributklassenmember"*Member*"|
|[Compilerfehler C3094](compiler-error-c3094.md)|"*Attribut*': anonyme Verwendung ist nicht zulässig.|
|[Compilerfehler C3095](compiler-error-c3095.md)|"*Attribut*": Attribut kann nicht wiederholt werden|
|[Compilerfehler C3096](compiler-error-c3096.md)|"*Attribut*": Attribut ist für Datenmember von Attributklassen nur zulässig.|
|[Compilerfehler C3097](compiler-error-c3097.md)|"*Attribut*": Attribut beschränkt werden muss, mit ' Assembly:' oder ' Module: "|
|Compilerfehler Fehler C3098|"*Bezeichner*": Attribut hat keine benutzerdefinierten Konstruktoren|
|[Compilerfehler C3099](compiler-error-c3099.md)|"*Schlüsselwort*": Verwenden Sie [System:: AttributeUsageAttribute] / [Windows::Foundation::Metadata::AttributeUsageAttribute] für verwaltete/WinRT-Attribute|
