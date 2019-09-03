---
title: warning-Pragma
ms.date: 08/29/2019
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 9a79f0c4a9eed6b62e42f056f9d1994b44b57297
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216470"
---
# <a name="warning-pragma"></a>warning-Pragma

Aktiviert die selektive Änderung des Verhaltens der Compilerwarnmeldungen.

## <a name="syntax"></a>Syntax

> **#pragma Warnung (** \
> &nbsp;&nbsp;&nbsp;&nbsp;*warnungsspezifizierer* **:** *Warnung-Number-List*\
> &nbsp;&nbsp;&nbsp;&nbsp;[ **;** *warnungsspezifizierer* **:** *Warnung-Number-List* ...] **)** \
> **#pragma Warnung (Push** [ **,** *n* ] **)** \
> **#pragma Warnung (Pop)**

## <a name="remarks"></a>Hinweise

Die folgenden Parameter für Warnungsbezeichner stehen zur Verfügung.

|warning-specifier|Bedeutung|
|------------------------|-------------|
|*1, 2, 3, 4*|Wenden Sie die angegebene Ebene auf die angegebenen Warnung(en) an. Aktiviert auch eine angegebene Warnung, die standardmäßig deaktiviert ist.|
|*default*|Setzen Sie das Warnverhalten auf den Standardwert zurück. Aktiviert auch eine angegebene Warnung, die standardmäßig deaktiviert ist. Die Warnung wird auf der standardmäßigen dokumentierten Ebene generiert.<br /><br /> Weitere Informationen finden Sie unter [standardmäßig](../preprocessor/compiler-warnings-that-are-off-by-default.md)deaktivierte Compilerwarnungen.|
|*disable*|Geben Sie die angegebene Warnmeldung (en) nicht aus.|
|*Zeit*|Melden Sie die angegebenen Warnungen als Fehler.|
|*once*|Zeigen Sie die angegebene(n) Meldung(en) nur einmal an.|
|*Boots*|Schiebt den aktuellen Zustand des Pragmas auf den Stapel, deaktiviert die angegebene Warnung für die nächste Zeile und ruft dann den Warnungsstapel auf, sodass der Pragmazustand zurückgesetzt wird.|

Die folgende Codeanweisung veranschaulicht, dass ein Parameter `warning-number-list` mehrere Warnungsnummern enthalten kann und dass mehrere Parameter `warning-specifier` in der gleichen Pragmaanweisung angegeben werden können.

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

Diese Direktive entspricht funktionell dem folgenden Code:

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

Der Compiler fügt 4000 zu jeder Warnungsnummer zwischen 0 und 999 hinzu.

Bei Warnungszahlen im Bereich 4700–4999, die mit der Codegenerierung zusammenhängen, wird der Status der Warnung aktiviert, wenn der Compiler auf die geöffnete geschweifte Klammer einer Funktion stößt, und er bleibt für den Rest der Funktion aktiv. Die Verwendung des **Warning** -Pragmas in der Funktion zum Ändern des Zustands einer Warn Zahl, die größer als 4699 ist, wird erst nach dem Ende der Funktion wirksam. Im folgenden Beispiel wird die korrekte Platzierung von **Warning** -Pragmas veranschaulicht, um eine Code Generierungs Warnmeldung zu deaktivieren und dann wiederherzustellen.

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

Beachten Sie, dass im gesamten Funktions Rumpf die letzte Einstellung des **Warning** -Pragmas für die gesamte Funktion wirksam ist.

## <a name="push-and-pop"></a>Push und Pop

Das **Warning** -Pragma unterstützt auch die folgende Syntax, wobei *n* eine Warnstufe (1 bis 4) darstellt.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

Das Pragma `warning( push )` speichert den aktuellen Warnungs Status für jede Warnung. Das Pragma `warning( push, n )` speichert den aktuellen Status für jede Warnung und legt die globale Warnstufe auf *n*fest.

Das Pragma `warning( pop )` springt den letzten Warn Status, der auf dem Stapel abgelegt wurde. Alle Änderungen, die Sie am Warn Status zwischen *Push* und *Pop* vorgenommen haben, werden rückgängig gemacht. Betrachten Sie das folgende Beispiel:

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

Am Ende dieses Codes stellt *Pop* den Status jeder Warnung (einschließlich 4705, 4706 und 4707) an dem Anfang des Codes wieder her.

Wenn Sie Header Dateien schreiben, können Sie mithilfe von *Push* und *Pop* sicherstellen, dass von einem Benutzer vorgenommene Warn Zustandsänderungen nicht verhindern, dass die Header ordnungsgemäß kompiliert werden. Verwenden Sie *Push* am Anfang des Headers und des *Popups* am Ende. Wenn Sie z. b. über einen Header verfügen, der nicht ordnungsgemäß auf Warnstufe 4 kompiliert, ändert der folgende Code die Warnstufe in 3 und stellt dann die ursprüngliche Warnstufe am Ende der Kopfzeile wieder her.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

Weitere Informationen zu Compileroptionen, die Ihnen helfen, Warnungen zu unterdrücken, finden Sie unter [/fi](../build/reference/fi-name-forced-include-file.md) und [/w](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
