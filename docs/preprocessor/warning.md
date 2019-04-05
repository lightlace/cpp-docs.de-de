---
title: warning
ms.date: 11/04/2016
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 1341472af22582635207a2bdff93b4367fd59330
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037749"
---
# <a name="warning-pragma"></a>warning-Pragma
Aktiviert die selektive Änderung des Verhaltens der Compilerwarnmeldungen.

## <a name="syntax"></a>Syntax

```
#pragma warning(
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )
#pragma warning( push[ ,n ] )
#pragma warning( pop )
```

## <a name="remarks"></a>Hinweise

Die folgenden Parameter für Warnungsbezeichner stehen zur Verfügung.

|warning-specifier|Bedeutung|
|------------------------|-------------|
|*1, 2, 3, 4*|Wenden Sie die angegebene Ebene auf die angegebenen Warnung(en) an. Dadurch aktiviert sich auch eine angegebene Warnung, die standardmäßig deaktiviert ist.|
|*default*|Setzen Sie das Warnverhalten auf den Standardwert zurück. Dadurch aktiviert sich auch eine angegebene Warnung, die standardmäßig deaktiviert ist. Die Warnung wird auf der standardmäßigen dokumentierten Ebene generiert.<br /><br /> Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|*Deaktivieren*|Geben Sie die angegebene(n) Warnung(en) nicht aus.|
|*error*|Melden Sie die angegebenen Warnungen als Fehler.|
|*once*|Zeigen Sie die angegebene(n) Meldung(en) nur einmal an.|
|*Unterdrücken*|Schiebt den aktuellen Zustand des Pragmas auf den Stapel, deaktiviert die angegebene Warnung für die nächste Zeile und ruft dann den Warnungsstapel auf, sodass der Pragmazustand zurückgesetzt wird.|

Die folgende Codeanweisung veranschaulicht, dass ein Parameter `warning-number-list` mehrere Warnungsnummern enthalten kann und dass mehrere Parameter `warning-specifier` in der gleichen Pragmaanweisung angegeben werden können.

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

Dies entspricht hinsichtlich der Funktion dem folgenden Code.

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

Der Compiler fügt 4000 zu jeder Warnungsnummer zwischen 0 und 999 hinzu.

Bei Warnungszahlen im Bereich 4700–4999, die mit der Codegenerierung zusammenhängen, wird der Status der Warnung aktiviert, wenn der Compiler auf die geöffnete geschweifte Klammer einer Funktion stößt, und er bleibt für den Rest der Funktion aktiv. Mithilfe der **Warnung** Pragma in die Funktion, die den Status einer Warnung zu ändern, die eine Zahl größer als 4699 aufweist werden erst dann wirksam nach dem Ende der Funktion. Das folgende Beispiel zeigt die korrekte Platzierung des **Warnung** Pragmas codeerstellung Warnmeldung angezeigt wird, deaktivieren und anschließenden Wiederherstellung.

```cpp
// pragma_warning.cpp
// compile with: /W1
#pragma warning(disable:4700)
void Test() {
   int x;
   int y = x;   // no C4700 here
   #pragma warning(default:4700)   // C4700 enabled after Test ends
}

int main() {
   int x;
   int y = x;   // C4700
}
```

Beachten Sie, die im gesamten Funktionstext die letzte Einstellung des der **Warnung** Pragma wird für die gesamte Funktion wirksam werden.

## <a name="push-and-pop"></a>Push und Pop

Die **Warnung** Pragma unterstützt auch die folgende Syntax, wobei *n* eine Warnstufe (1 bis 4) dar.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

Das Pragma `warning( push )` speichert den aktuellen Warnzustand für jede Warnung. Das Pragma `warning( push, n )` speichert den aktuellen Zustand für jede Warnung und legt die globale Warnstufe auf *n*.

Das Pragma `warning( pop )` Pops, die der letzte Warnzustand auf dem Stapel abgelegt. Alle Änderungen, die Sie in "Warnung" zwischen vorgenommen *Push* und *pop* werden rückgängig gemacht werden. Betrachten Sie das folgende Beispiel:

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

Am Ende dieses Codes *pop* stellt den Zustand jeder Warnung wieder her (einschließlich 4705, 4706 und 4707), sie am Anfang des Codes was.

Wenn Sie Headerdateien schreiben, können Sie *Push* und *pop* um sicherzustellen, dass-Status "Warnung" der Änderungen von einem Benutzer nicht die Header verhindern ordnungsgemäß kompiliert. Verwendung *Push* zu Beginn des Headers und *pop* am Ende. Wenn Sie beispielsweise über einen Header verfügen, der nicht ordnungsgemäß auf Warnstufe 4 kompiliert, würde der folgende Code die Warnstufe auf 3 ändern und anschließend die ursprüngliche Warnstufe am Ende des Headers wiederherstellen.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

Weitere Informationen zu Compileroptionen, die Optionen, mit denen Sie unterdrückt Warnungen, finden Sie unter [/Fi](../build/reference/fi-name-forced-include-file.md) und [/w](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)