---
title: Compilerfehler Fehler C3100 über C3199 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
helpviewer_keywords:
- C3102
- C3105
- C3107
- C3108
- C3109
- C3111
- C3112
- C3119
- C3122
- C3123
- C3124
- C3125
- C3127
- C3128
- C3129
- C3143
- C3144
- C3146
- C3147
- C3148
- C3151
- C3158
- C3164
- C3165
- C3169
- C3177
- C3178
- C3184
- C3188
- C3191
- C3193
dev_langs:
- C++
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 062ab968a51c38e9418a96b0df07eec3ae399ac3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283893"
---
# <a name="compiler-errors-c3100-through-c3199"></a>Compilerfehler Fehler C3100 über C3199 generiert

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C3100](compiler-error-c3100.md)|"*Bezeichner*': Unbekanntes Attribut-Qualifizierer|
|[Compilerfehler C3101](compiler-error-c3101.md)|Ungültiger Ausdruck für das benannte Attributargument "*Bezeichner*"|
|Compilerfehler Fehler C3102|Veraltet.|
|[Compilerfehler C3103](compiler-error-c3103.md)|"*Bezeichner*': das benannte Argument wiederholt|
|[Compilerfehler C3104](compiler-error-c3104.md)|Unzulässiges Attributargument.|
|Compilerfehler Fehler C3105|"*Symbol*": kann nicht als Attribut verwendet werden|
|[Compilerfehler C3106](compiler-error-c3106.md)|"*Attribut*": unbenannte Argumente müssen vor benannte Argumenten stehen.|
|Compilerfehler Fehler C3107|"*Attribut*": Memberfunktionen systemeigener Attribute können nicht definiert werden|
|Compilerfehler Fehler C3108|einen Typ kann nicht hergeleitet werden, da es sich bei eine Initialisiererliste kein Ausdruck ist|
|Compilerfehler Fehler C3109|"*Bezeichner*': Schnittstellenmethoden müssen entweder die '__stdcall' oder"__cdecl"-Aufrufkonvention verwenden|
|[Compilerfehler C3110](compiler-error-c3110.md)|"*Funktion*": kann nicht überladen eine COM-Schnittstellen-Methode|
|Compilerfehler Fehler C3111|Eine Initialisiererliste kann nicht als das Standardargument für einen Vorlagenparameter verwendet werden|
|Compilerfehler Fehler C3112|"*Schnittstelle*': eine Schnittstelle kann nur im globalen deklariert werden oder Namespacebereich|
|[Compilerfehler C3113](compiler-error-c3113.md)|"Schnittstelle/Enum" darf keine Vorlagen-/generische sein.|
|[Compilerfehler C3114](compiler-error-c3114.md)|"*Bezeichner*': kein gültiges benanntes Attributargument.|
|[Compilerfehler C3115](compiler-error-c3115.md)|"*Attribut*": Dieses Attribut ist nicht zulässig, auf "*erstellen*"|
|[Compilerfehler C3116](compiler-error-c3116.md)|"*Spezifizierer*': Ungültige Speicherklasse für Schnittstellen-Methode|
|[Compilerfehler C3117](compiler-error-c3117.md)|"*Schnittstelle*': eine Schnittstelle kann nur eine Basisklasse haben|
|[Compilerfehler C3118](compiler-error-c3118.md)|"*Schnittstelle*": Schnittstellen unterstützen keine virtuellen Vererbung|
|Compilerfehler Fehler C3119|alignas(void) ist nicht zulässig.|
|[Compilerfehler C3120](compiler-error-c3120.md)|"*Bezeichner*': Schnittstellenmethoden keine Liste variabler Argumente akzeptiert|
|[Compilerfehler C3121](compiler-error-c3121.md)|GUID kann nicht geändert werden, für die Klasse*Klasse*"|
|Compilerfehler Fehler C3122|"*Schnittstelle*': eine generische WinRT-Schnittstelle sind keine GUID|
|Compilerfehler Fehler C3123|WinRT generische Schnittstelle darf keine Einschränkungen aufweisen.|
|Compilerfehler Fehler C3124|"signed Char" ist kein gültiger Typ WinRT Daten. Verwenden Sie stattdessen "unsigned Char", "Wchar_t" oder "Short mit Vorzeichen".|
|Compilerfehler Fehler C3125|"*Typ*': Typ kann nicht direkt oder indirekt abgeleitet"Platform:: Exception"|
|[Compilerfehler C3126](compiler-error-c3126.md)|eine Union kann nicht definiert "*Union*"innerhalb von verwaltetem/WinRT-Typ"*Typ*"|
|Compilerfehler Fehler C3127|"*Typ*": "*Merkmals*" Merkmal "" kann nur verwendet werden, auf eine Verweisklasse WinRT|
|Compilerfehler Fehler C3128|"*Typ*"besitzt keine vtable enthält, der von eingeführt wurde"*Typ*"|
|Compilerfehler Fehler C3129|"*Typ*': __default_vptr_for_base kann nur verwendet werden, auf die lokal definierte polymorphen Typen und Basen|
|[Compilerfehler C3130](compiler-error-c3130.md)|Interner Compilerfehler: Fehler bei eingefügten Codeblock in PDB-Datei schreiben|
|[Compilerfehler C3131](compiler-error-c3131.md)|Projekt muss ein 'Module'-Attribut mit der Eigenschaft "Name" aufweisen.|
|[Compilerfehler C3132](compiler-error-c3132.md)|"*Parameter*': Parameterarrays können nur auf einem formalen Argument vom Typ 'eindimensionalem verwaltet/WinRT-Array' angewendet werden|
|[Compilerfehler C3133](compiler-error-c3133.md)|Attribute können nicht auf C++-Variablenargumente angewendet werden|
|[Compilerfehler C3134](compiler-error-c3134.md)|"*Wert*": Wert Attributargument '*Argument*"enthält keinen gültigen Typ"*Typ*"|
|[Compilerfehler C3135](compiler-error-c3135.md)|"*Bezeichner*': eine Eigenschaft kann nicht"Const"aufweisen, oder geben Sie"volatile"|
|[Compilerfehler C3136](compiler-error-c3136.md)|"*Schnittstelle*': eine COM-Schnittstelle kann nur von einem anderen COM-Schnittstelle erben '*Schnittstelle*' ist keine COM-Schnittstelle|
|[Compilerfehler C3137](compiler-error-c3137.md)|"*Bezeichner*': eine Eigenschaft kann nicht initialisiert werden|
|[Compilerfehler C3138](compiler-error-c3138.md)|"*Bezeichner*': eine"*Attribut*"Schnittstelle muss von IDispatch oder von einer Schnittstelle, die von IDispatch erbt erben.|
|[Compilerfehler C3139](compiler-error-c3139.md)|"*Typ*': einen UDT ohne Mitglieder kann nicht exportiert werden.|
|[Compilerfehler C3140](compiler-error-c3140.md)|mehrere "Module"-Attribute können nicht in der gleichen Kompilierungseinheit verwenden werden.|
|[Compilerfehler C3141](compiler-error-c3141.md)|"*Schnittstelle*": Schnittstellen unterstützen nur öffentliche Vererbung|
|[Compilerfehler C3142](compiler-error-c3142.md)|"*Eigenschaft*': Sie können die Adresse einer Eigenschaft nicht übernehmen|
|Compilerfehler Fehler C3143|"*Argument*": Attribute-Argument kann nicht mehrere Werte aufweisen|
|Compilerfehler Fehler C3144|"*Attribut*": Attribut erfordert explizite Argumente "*Argument*" unbenannt|
|[Compilerfehler C3145](compiler-error-c3145.md)|"*Bezeichner*': globale oder statische Variable hat möglicherweise keinen verwalteten/WinRT-Typ"*Typ*"|
|Compilerfehler Fehler C3146|Veraltet.|
|Compiler-Fehler C3147 generiert|Veraltet.|
|Compilerfehler Fehler C3148|Veraltet.|
|[Compilerfehler C3149](compiler-error-c3149.md)|"*Typ*': Dieser Typ ohne einen auf oberster Ebene verwenden darf nicht '*token*"|
|[Compilerfehler C3150](compiler-error-c3150.md)|"*erstellen*": "*Attribut*" kann nur auf eine Klasse, Struktur, Schnittstelle, Array oder Zeiger angewendet werden|
|Compilerfehler Fehler C3151|Veraltet.|
|[Compilerfehler C3152](compiler-error-c3152.md)|"*Funktion*": "*Schlüsselwort*" kann nur auf eine Klasse, Struktur oder virtuelle Memberfunktion angewendet werden|
|[Compilerfehler C3153](compiler-error-c3153.md)|"*Schnittstelle*': Sie können keine Instanz einer Schnittstelle erstellen|
|[Compilerfehler C3154](compiler-error-c3154.md)|Erwartet ',', bevor Sie mit den Auslassungspunkten. Nicht durch Trennzeichen getrennte Auslassungszeichen werden unter Parameter Array-Funktionen nicht unterstützt.|
|[Compilerfehler C3155](compiler-error-c3155.md)|Attribute sind in einem Eigenschaft-Indexer nicht zulässig.|
|[Compilerfehler C3156](compiler-error-c3156.md)|"*Klasse*': eine lokale Definition eines verwalteten/WinRT-Typs keine|
|[Compilerfehler C3157](compiler-error-c3157.md)|ParamArray-Attribut kann nur auf den letzten Parameter angewendet werden|
|Compilerfehler Fehler C3158|"*Funktion*": "*Schlüsselwort*" kann nur auf eine virtuelle Memberfunktion angewendet werden|
|[Compilerfehler C3159](compiler-error-c3159.md)|"*Bezeichner*': Array von Zeigern auf Werttyp kann nicht deklariert werden|
|[Compilerfehler C3160](compiler-error-c3160.md)|"*Typ*": ein Datenmember einer verwalteten/WinRT-Klasse kann nicht diesen Typ aufweisen|
|[Compilerfehler C3161](compiler-error-c3161.md)|"*Schnittstelle*": schachteln Klasse, Struktur oder Schnittstelle in einer Schnittstelle ist nicht zulässig; das Schachteln einer Schnittstelle in einer Klasse oder Struktur ist nicht zulässig|
|[Compilerfehler C3162](compiler-error-c3162.md)|"*Typ*": ein Verweistyp mit einem Destruktor kann nicht als Typ des statischen Datenmember verwendet werden "*Member*"|
|[Compilerfehler C3163](compiler-error-c3163.md)|"*Klasse*": Attribute, die mit der vorherigen Deklaration nicht konsistent.|
|Compilerfehler Fehler C3164|Veraltet.|
|Compilerfehler Fehler C3165|"*Wert*": kann nicht in einen Ganzzahl- oder Gleitkommawert konvertiert werden|
|[Compilerfehler C3166](compiler-error-c3166.md)|Veraltet. "*Typ*": ein Datenmember einer verwalteten/WinRT-Klasse keinen Typ "*Pointer_type* zu inneren *Managed_pointer_type*"|
|[Compilerfehler C3167](compiler-error-c3167.md)|Kann nicht initialisiert werden, .NET Framework: Stellen Sie sicher, dass es installiert ist|
|[Compilerfehler C3168](compiler-error-c3168.md)|"*Typ*": Ungültiger zugrunde liegender Typ für Enumeration|
|Compilerfehler Fehler C3169|"*Typ*': Typ für 'Auto' kann nicht aus hergeleitet"*Typ*"|
|[Compilerfehler C3170](compiler-error-c3170.md)|keine anderen Modulbezeichner in einem Projekt|
|[Compilerfehler C3171](compiler-error-c3171.md)|"*Modul*": Geben Sie andere Modulattribute kann nicht in einem Projekt|
|[Compilerfehler C3172](compiler-error-c3172.md)|"*Bezeichner*": Geben Sie unterschiedliche Idl_module-Attribute können nicht in einem Projekt|
|[Compilerfehler C3173](compiler-error-c3173.md)|Versionskonflikt bei Merge von idl|
|[Compilerfehler C3174](compiler-error-c3174.md)|Modulattribut wurde nicht angegeben.|
|[Compilerfehler C3175](compiler-error-c3175.md)|"*Funktion*': eine Methode eines verwalteten Typs kann nicht aufgerufen werden, von nicht verwalteten Funktion"*Funktion*"|
|[Compilerfehler C3176](compiler-error-c3176.md)|"*Typ*": lokale Werttyp kann nicht deklariert werden.|
|Compilerfehler Fehler C3177|eine Umwandlungsfunktion in einen Typ, enthält keine "*Typ*"|
|Compilerfehler Fehler C3178|"*Typ*": ParamArray in einer Funktion mit Standardargumenten können keine|
|[Compilerfehler C3179](compiler-error-c3179.md)|ein unbenannter verwaltet/WinRT-Typ ist nicht zulässig.|
|[Compilerfehler C3180](compiler-error-c3180.md)|"*Typ*": Name überschreitet Metadatenlimit von '*Anzahl*' Zeichen|
|[Compilerfehler C3181](compiler-error-c3181.md)|"*Typ*": Ungültiger Operand für *Operator*|
|[Compilerfehler C3182](compiler-error-c3182.md)|"*Typ*': eine using-Deklaration oder Zugriffsdeklaration für Member ist innerhalb eines verwalteten/WinRT-Typs nicht zulässig|
|[Compilerfehler C3183](compiler-error-c3183.md)|keine unbenannte Klasse, Struktur oder Union innerhalb der verwalteten/WinRT-Typ definieren "*Klasse*"|
|Compilerfehler Fehler C3184|Veraltet.|
|[Compilerfehler C3185](compiler-error-c3185.md)|"Typeid": auf verwalteten/WinRT-Typs verwendet "*Typ*", verwenden Sie "*Operator*" stattdessen|
|Compilerfehler C3186|Veraltet.|
|[Compilerfehler C3187](compiler-error-c3187.md)|"*Bezeichner*": ist nur innerhalb des Texts einer Funktion verfügbar|
|Compilerfehler Fehler C3188|Veraltet.|
|[Compilerfehler C3189](compiler-error-c3189.md)|"Typeid <*Deklarator*>": Diese Syntax ist nicht mehr unterstützt, use::typeid stattdessen|
|[Compilerfehler C3190](compiler-error-c3190.md)|"*Deklarator*"mit den bereitgestellten Vorlagenargumenten ist nicht die explizite Instanziierung der Memberfunktionen von"*Typ*"|
|Compiler-Fehler C3191 generiert|Veraltet.|
|[Compilerfehler C3192](compiler-error-c3192.md)|Syntaxfehler: "^" ist kein Präfixoperator (meinten Sie ' *'?)|
|Compilerfehler Fehler C3193|"*erstellen*": erfordert "/ Clr" oder "/ ZW" Befehlszeilenoption|
|[Compilerfehler C3194](compiler-error-c3194.md)|"*Typ*": ein Werttyp keinen Zuweisungsoperator|
|[Compilerfehler C3195](compiler-error-c3195.md)|"*Schlüsselwort*": ist reserviert und kann nicht als Mitglied einer Ref oder eines Werttyps verwendet werden. CLR/WinRT-Operatoren müssen mit dem Schlüsselwort "Operator" definiert werden|
|[Compilerfehler C3196](compiler-error-c3196.md)|"*Bezeichner*": mehrmals verwendet|
|[Compilerfehler C3197](compiler-error-c3197.md)|"*Schlüsselwort*": kann nur in Definitionen verwendet werden|
|[Compilerfehler C3198](compiler-error-c3198.md)|Ungültige Verwendung eines Gleitkommapragmas: Fenv_access-Pragma unterstützt nur im präzise-Modus|
|[Compilerfehler C3199](compiler-error-c3199.md)|Ungültige Verwendung eines Gleitkommapragmas: Ausnahmen werden in nicht-präzisen Modus nicht unterstützt.|
