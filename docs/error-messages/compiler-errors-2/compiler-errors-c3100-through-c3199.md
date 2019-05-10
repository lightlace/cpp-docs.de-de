---
title: Compilerfehler C3100 bis C3199
ms.date: 04/21/2019
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
ms.assetid: 7bc40c2f-6a8d-488a-b665-f39375afee77
ms.openlocfilehash: efa3207a9fdfb81a52bf319a1cbc2da84084b6cd
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856823"
---
# <a name="compiler-errors-c3100-through-c3199"></a>Compilerfehler C3100 bis C3199

Die Artikel in diesem Abschnitt der Dokumentation wird erläutert, eine Teilmenge der Fehlermeldungen, die vom Compiler generiert werden.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Fehlermeldungen

|Fehler|Meldung|
|-----------|-------------|
|[Compilerfehler C3100](compiler-error-c3100.md)|"*Bezeichner*": Unbekannter Attributqualifizierer|
|[Compilerfehler C3101 generiert](compiler-error-c3101.md)|Ungültiger Ausdruck für benanntes Attributargument "*Bezeichner*"|
|Compilerfehler C3102|Veraltet.|
|[Compilerfehler C3103 generiert](compiler-error-c3103.md)|"*Bezeichner*": wiederholtes benanntes Argument|
|[Compilerfehler C3104](compiler-error-c3104.md)|Unzulässiges Attributargument.|
|Compilerfehler C3105|"*Symbol*": kann nicht als Attribut verwendet werden|
|[Compilerfehler C3106 generiert](compiler-error-c3106.md)|"*Attribut*": unbenannte Argumente müssen vor benannte Argumenten stehen.|
|Compilerfehler C3107|"*Attribut*": Memberfunktionen systemeigener Attribute können nicht definiert werden|
|Compilerfehler C3108|einen Typ kann nicht hergeleitet werden, da eine Initialisiererliste kein Ausdruck ist.|
|Compilerfehler C3109|"*Bezeichner*": Schnittstellenmethoden müssen entweder die "__stdcall" oder "__cdecl"-Aufrufkonvention verwenden|
|[Compilerfehler C3110](compiler-error-c3110.md)|"*Funktion*": COM-Schnittstellenmethode kann nicht überladen|
|Compilerfehler C3111|Eine Initialisiererliste kann nicht als Standardargument für einen Vorlagenparameter verwendet werden|
|Compilerfehler C3112|"*Schnittstelle*': eine Schnittstelle kann nur im globalen deklariert werden oder im Namespacebereich|
|[Compilerfehler C3113](compiler-error-c3113.md)|eine "Schnittstelle/Enum" darf keine Vorlagen-/generische sein.|
|[Compilerfehler C3114 generiert](compiler-error-c3114.md)|"*Bezeichner*': kein gültiges benanntes Attributargument.|
|[Compilerfehler C3115 generiert](compiler-error-c3115.md)|"*Attribut*": Dieses Attribut darf nicht auf '*erstellen*"|
|[Compilerfehler C3116 generiert](compiler-error-c3116.md)|"*Spezifizierer*': Ungültige Speicherklasse für Schnittstellenmethode|
|[Compilerfehler C3117 generiert](compiler-error-c3117.md)|"*Schnittstelle*': eine Schnittstelle kann nur eine Basisklasse besitzen|
|[Compilerfehler C3118](compiler-error-c3118.md)|"*Schnittstelle*": Schnittstellen unterstützen keine virtuellen Vererbung|
|Compilerfehler C3119|alignas(void) ist nicht zulässig|
|[Compilerfehler C3120](compiler-error-c3120.md)|"*Bezeichner*": Schnittstellenmethoden können nicht mit eine Liste variabler Argumente werden|
|[Compilerfehler C3121](compiler-error-c3121.md)|GUID kann nicht geändert werden, für die Klasse*Klasse*"|
|Compilerfehler C3122|"*Schnittstelle*': eine generische WinRT-Schnittstelle darf keine GUID aufweisen.|
|Compilerfehler C3123|Generische WinRT-Schnittstelle darf keine Einschränkungen aufweisen.|
|Compilerfehler C3124|"signed Char" ist kein gültiger Typ für WinRT-Daten. Verwenden Sie stattdessen "unsigned Char", "Wchar_t" oder "signed Short".|
|Compilerfehler C3125|"*Typ*': Typ kann nicht direkt oder indirekt abgeleitet werden von"Platform:: Exception"|
|[Compilerfehler C3126 generiert](compiler-error-c3126.md)|eine Union kann nicht definiert werden kann '*Union*"in verwalteten/WinRT-Typ'*Typ*"|
|Compilerfehler C3127|"*Typ*': '*Merkmal*" Eigenschaft kann nur auf eine WinRT-Verweisklasse verwendet werden|
|Compilerfehler C3128|"*Typ*'besitzt keine vtable enthält, die vom eingeführt wurde'*Typ*"|
|Compilerfehler C3129|"*Typ*": __default_vptr_for_base kann nur auf lokal definierten polymorphen Typen und Basen verwendet werden|
|[Compilerfehler C3130](compiler-error-c3130.md)|Interner Compilerfehler: Fehler beim Schreiben von Eingefügter Codeblock in PDB-Datei|
|[Compilerfehler C3131 generiert](compiler-error-c3131.md)|Projekt muss ein "Modulattribut" mit der Eigenschaft "Name" aufweisen.|
|[Compilerfehler C3132 generiert](compiler-error-c3132.md)|"*Parameter*": Parameterarrays können nur auf formale Argumente vom Typ "eindimensionales verwaltet/WinRT-Array" angewendet werden|
|[Compilerfehler C3133 generiert](compiler-error-c3133.md)|Attribute können nicht auf Varargs in C++ angewendet werden|
|[Compilerfehler C3134](compiler-error-c3134.md)|"*Wert*': Wert des Attributarguments"*Argument*'hat keinen gültigen Typ'*Typ*"|
|[Compilerfehler C3135](compiler-error-c3135.md)|"*Bezeichner*': eine Eigenschaft darf keinen"Const"oder"volatile"Geben|
|[Compilerfehler C3136 generiert](compiler-error-c3136.md)|"*Schnittstelle*': eine COM-Schnittstelle kann nur von einem anderen COM-Schnittstelle erben"*Schnittstelle*' ist keine COM-Schnittstelle|
|[Compilerfehler C3137 generiert](compiler-error-c3137.md)|"*Bezeichner*': eine Eigenschaft kann nicht initialisiert werden|
|[Compilerfehler C3138 generiert](compiler-error-c3138.md)|"*Bezeichner*": ein "*Attribut*" Schnittstelle muss von IDispatch oder von einer Schnittstelle, die von IDispatch erbt erben.|
|[Compilerfehler C3139](compiler-error-c3139.md)|"*Typ*": einen UDT ohne Mitglieder können nicht exportiert werden.|
|[Compilerfehler C3140](compiler-error-c3140.md)|mehrere "Module"-Attribute können nicht in der gleichen Kompilationseinheit verwenden werden.|
|[Compilerfehler C3141 generiert](compiler-error-c3141.md)|"*Schnittstelle*": Schnittstellen unterstützen nur öffentliche Vererbung|
|[Compilerfehler C3142](compiler-error-c3142.md)|"*Eigenschaft*': Sie können die Adresse einer Eigenschaft nicht übernehmen|
|Compilerfehler C3143|"*Argument*': Codeattribut-Arguments darf nicht mehrere Werte aufweisen|
|Compilerfehler C3144|"*Attribut*": Attribut erfordert explizite Argumente "*Argument*" unbenannt ist|
|[Compilerfehler C3145](compiler-error-c3145.md)|"*Bezeichner*': globale oder statische Variable möglicherweise nicht verwaltete/WinRT-Typ '*Typ*"|
|Compilerfehler C3146|Veraltet.|
|Compilerfehler C3147 generiert|Veraltet.|
|Compilerfehler C3148|Veraltet.|
|[Compilerfehler C3149 generiert](compiler-error-c3149.md)|"*Typ*': Dieser Typ ohne oberster Ebene kann nicht verwendet '*token*"|
|[Compilerfehler C3150](compiler-error-c3150.md)|"*erstellen*': '*Attribut*' kann nur auf eine Klasse, Struktur, Schnittstelle, Array oder Zeiger angewendet werden|
|Compilerfehler C3151|Veraltet.|
|[Compilerfehler C3152](compiler-error-c3152.md)|"*Funktion*': '*Schlüsselwort*' kann nur auf eine Klasse, Struktur oder virtuelle Memberfunktion angewendet werden|
|[Compilerfehler C3153](compiler-error-c3153.md)|"*Schnittstelle*': Sie können keine Instanz einer Schnittstelle erstellen|
|[Compilerfehler C3154 generiert](compiler-error-c3154.md)|Erwartet ',', bevor Sie mit den Auslassungspunkten. Nicht durch Trennzeichen getrennt, mit den Auslassungspunkten für Parameterarrayfunktionen nicht unterstützt wird.|
|[Compilerfehler C3155 generiert](compiler-error-c3155.md)|in einem Eigenschaftenindexer sind keine Attribute zulässig.|
|[Compilerfehler C3156](compiler-error-c3156.md)|"*Klasse*": keine lokale Definition eines verwalteten/WinRT-Typs|
|[Compilerfehler C3157](compiler-error-c3157.md)|ParamArray-Attribut kann nur auf den letzten Parameter angewendet werden|
|Compilerfehler C3158|"*Funktion*': '*Schlüsselwort*' kann nur auf eine virtuelle Memberfunktion angewendet werden|
|[Compilerfehler C3159](compiler-error-c3159.md)|"*Bezeichner*": Array von Zeigern auf Typ kann nicht deklariert werden|
|[Compilerfehler C3160](compiler-error-c3160.md)|"*Typ*": ein Datenmember einer verwalteten/WinRT-Klasse kann nicht diesen Typ aufweisen|
|[Compilerfehler C3161 generiert](compiler-error-c3161.md)|"*Schnittstelle*': Schachteln von Klasse, Struktur oder Schnittstelle in einer Schnittstelle ist nicht zulässig; das Schachteln einer Schnittstelle in einer Klasse oder Struktur ist nicht zulässig|
|[Compilerfehler C3162 generiert](compiler-error-c3162.md)|"*Typ*": ein Verweistyp mit einem Destruktor kann nicht verwendet werden, wie der Typ des statischen Datenmembers "*Member*"|
|[Compilerfehler C3163](compiler-error-c3163.md)|"*Klasse*": Attribute, die mit der vorherigen Deklaration inkonsistent.|
|Compilerfehler C3164|Veraltet.|
|Compilerfehler C3165|"*Wert*": kann nicht in einen Ganzzahl-oder Fließkommawert-Wert konvertiert werden|
|[Compilerfehler C3166](compiler-error-c3166.md)|Veraltet. "*Typ*": ein Datenmember einer verwalteten/WinRT-Klasse kann keinen Typ aufweisen '*Pointer_type* zu inneren *Managed_pointer_type*"|
|[Compilerfehler C3167](compiler-error-c3167.md)|Kann nicht initialisiert werden .NET Framework: Stellen Sie sicher, dass es installiert wurde|
|[Compilerfehler C3168 generiert](compiler-error-c3168.md)|"*Typ*': Ungültiger zugrunde liegender Typ für Enumeration|
|Compilerfehler C3169|"*Typ*': Typ für"Auto"kann nicht hergeleitet werden, von"*Typ*"|
|[Compilerfehler C3170](compiler-error-c3170.md)|in einem Projekt können nicht verschiedene Modulbezeichner haben werden.|
|[Compilerfehler C3171](compiler-error-c3171.md)|"*Modul*': können keine verschiedenen Modulattribute in einem Projekt|
|[Compilerfehler C3172](compiler-error-c3172.md)|"*Bezeichner*": Geben Sie unterschiedliche Idl_module-Attribute können nicht in einem Projekt|
|[Compilerfehler C3173](compiler-error-c3173.md)|Versionskonflikt beim Zusammenführen von idl|
|[Compilerfehler C3174](compiler-error-c3174.md)|Das Modulattribut wurde nicht angegeben.|
|[Compilerfehler C3175 generiert](compiler-error-c3175.md)|"*Funktion*': eine Methode eines verwalteten Typs kann nicht aufgerufen werden, von nicht verwalteten Funktion"*Funktion*"|
|[Compilerfehler C3176 generiert](compiler-error-c3176.md)|"*Typ*": ein lokaler Werttyp kann nicht deklariert|
|Compilerfehler C3177|kann Ihnen keine Konvertierungsfunktion in einen Typ mit "*Typ*"|
|Compilerfehler C3178|"*Typ*": ParamArray kann in einer Funktion mit Standardargumenten nicht verwendet|
|[Compilerfehler C3179](compiler-error-c3179.md)|ein nicht verwaltete/WinRT-Typ ist nicht zulässig.|
|[Compilerfehler C3180](compiler-error-c3180.md)|"*Typ*": Name ist länger als das Metadatenlimit von "*Anzahl*' Zeichen|
|[Compilerfehler C3181 generiert](compiler-error-c3181.md)|"*Typ*': Ungültiger Operand für *Operator*|
|[Compilerfehler C3182](compiler-error-c3182.md)|"*Typ*': eine using- oder Zugriffsdeklaration für Member ist innerhalb eines verwalteten/WinRT-Typs nicht zulässig|
|[Compilerfehler C3183](compiler-error-c3183.md)|kann nicht definiert, unbenannte Klasse, Struktur oder Union innerhalb verwaltet/WinRT-Typ '*Klasse*"|
|Compilerfehler C3184|Veraltet.|
|[Compilerfehler C3185 generiert](compiler-error-c3185.md)|"Typeid": für verwaltete/WinRT-Typ verwendet "*Typ*", verwenden Sie '*Operator*"stattdessen|
|Compilerfehler C3186 generiert|Veraltet.|
|[Compilerfehler C3187](compiler-error-c3187.md)|"*Bezeichner*": ist nur im Text einer Funktion verfügbar|
|Compilerfehler C3188|Veraltet.|
|[Compilerfehler C3189 generiert](compiler-error-c3189.md)|"Typeid <*Deklarator*>': Diese Syntax ist nicht mehr unterstützt,":: typeid "stattdessen|
|[Compilerfehler C3190](compiler-error-c3190.md)|"*Deklarator*"mit den bereitgestellten Vorlagenargumenten ist nicht die explizite Instanziierung der Memberfunktionen von"*Typ*"|
|Compilerfehler C3191 generiert|Veraltet.|
|[Compilerfehler C3192 generiert](compiler-error-c3192.md)|Syntaxfehler: "^" ist kein Präfixoperator (meinten Sie "*"?)|
|Compilerfehler C3193|"*erstellen*": erfordert "/ Clr" oder "/ ZW" Befehlszeilenoption|
|[Compilerfehler C3194 generiert](compiler-error-c3194.md)|"*Typ*": ein Werttyp kann nicht keinen Zuweisungsoperator aufweisen|
|[Compilerfehler C3195](compiler-error-c3195.md)|"*Schlüsselwort*": ist reserviert und kann nicht als Mitglied einer Ref-Klasse oder eines Werttyps verwendet werden. CLR/WinRT-Operatoren müssen mit dem Schlüsselwort "Operator" definiert werden|
|[Compilerfehler C3196 generiert](compiler-error-c3196.md)|"*Bezeichner*": mehrmals verwendet|
|[Compilerfehler C3197 aus](compiler-error-c3197.md)|"*Schlüsselwort*": kann nur in Definitionen verwendet werden|
|[Compilerfehler C3198 generiert](compiler-error-c3198.md)|Ungültige Verwendung von Gleitkommapragmas: Fenv_access-Pragma wird nur im precise-Modus ausgeführt.|
|[Compilerfehler C3199](compiler-error-c3199.md)|Ungültige Verwendung von Gleitkommapragmas: Ausnahmen werden in nicht dem precise-Modus nicht unterstützt|

## <a name="see-also"></a>Siehe auch

[C /C++ Compiler- und Build tools, Fehler und Warnungen](../compiler-errors-1/c-cpp-build-errors.md) \
[Compilerfehler C2000 - C3999](../compiler-errors-1/compiler-errors-c2000-c3999.md)
