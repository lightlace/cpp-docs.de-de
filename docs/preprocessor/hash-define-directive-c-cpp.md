---
title: '##define-Direktive (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#define'
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
ms.openlocfilehash: 8a0cc7e7836a0c82c72055fe8d9e7497995485d0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039499"
---
# <a name="define-directive-cc"></a>#define-Direktive (C/C++)

Die **#define** erstellt eine *Makro*, d.h., dass die Zuordnung eines Bezeichners oder parametrisierten Bezeichners zu einer tokenzeichenkette darstellt. Nachdem das Makro definiert wurde, kann der Compiler die Tokenzeichenkette für jedes Vorkommen des Bezeichners in der Quelldatei ersetzen.

## <a name="syntax"></a>Syntax

`#define` *identifier* *token-string*<sub>opt</sub>

`#define` *Bezeichner* `(` *Bezeichner*<sub>opt</sub> `,` *...*  `,` *Bezeichner*<sub>opt</sub> `)` *-Token-Zeichenfolge*<sub>deaktivieren</sub>

## <a name="remarks"></a>Hinweise

Die **#define** -Direktive weist den Compiler ersetzen *-Token-Zeichenfolge* jedes Vorkommen von *Bezeichner* in der Quelldatei. Die *Bezeichner* wird nur ersetzt, wenn er ein Token bildet. D. h. *Bezeichner* wird nicht ersetzt werden, wenn es in einem Kommentar, in eine Zeichenfolge oder als Teil eines längeren Bezeichners erscheint. Weitere Informationen finden Sie unter [Token](../cpp/tokens-cpp.md).

Die *-Token-Zeichenfolge* -Argument besteht aus einer Reihe von Token, z. B. Schlüsselwörter, Konstanten oder vollständigen Anweisungen. Müssen durch ein oder mehrere Leerzeichen getrennt *-Token-Zeichenfolge* aus *Bezeichner*. Diese Leerstelle und alle weiteren Leerstellen nach dem letzten Token des Texts werden nicht als Teil des ersetzten Texts betrachtet.

Ein `#define` ohne eine *-Token-Zeichenfolge* entfernt Vorkommen der *Bezeichner* aus der Quelldatei. Die *Bezeichner* bleibt definiert und kann getestet werden, mithilfe der `#if defined` und `#ifdef` Anweisungen.

Durch das zweite Syntaxformat wird ein funktionsähnliches Makro mit Parametern definiert. Dieses Formular akzeptiert eine optionale Liste von Parametern, die in Klammern angegeben sein müssen. Nachdem das Makro definiert, werden nachfolgende Vorkommen des ist *Bezeichner*( *Bezeichner*<sub>opt</sub>,..., *Bezeichner* <sub>opt</sub> ) wird mit einer Version von ersetzt die *-Token-Zeichenfolge* Argument, das tatsächliche Argumente, die durch formale Parameter ersetzt wurde.

Formale Parameternamen werden *-Token-Zeichenfolge* auf die Speicherorte zu markieren, in denen tatsächliche Werte ersetzt werden. Jeder Parametername kann mehrmals *-Token-Zeichenfolge*, und die Namen können in beliebiger Reihenfolge angezeigt werden. Die Anzahl von Argumenten im Aufruf muss mit der Anzahl von Parametern in der Makrodefinition übereinstimmen. Mit der großzügigen Verwendung von Klammern wird sichergestellt, dass komplexe tatsächliche Argumente richtig interpretiert werden.

Die formalen Parameter in der Liste werden durch Kommas getrennt. Jeder Name in der Liste muss eindeutig sein und die Liste muss in Klammern eingeschlossen werden. Keine Leerzeichen trennen können *Bezeichner* und die öffnende Klammer. Verwenden Sie die Zeilenverkettung, platzieren Sie einen umgekehrten Schrägstrich (`\`) unmittelbar vor dem Zeilenumbruchzeichen – für lange Direktive in mehreren Quellzeilen. Der Gültigkeitsbereich eines formalen Parameternamens erstreckt sich auch auf die neue Zeile, die endet *-Token-Zeichenfolge*.

Wenn ein Makro im zweiten Syntaxformat definiert wurde, geben nachfolgende Textinstanzen, auf die eine Argumentliste folgt, einen Makro-Aufruf an. Die tatsächlichen Argumente, die eine Instanz von *Bezeichner* in der Quelldatei folgen, stimmen mit den entsprechenden formalen Parameter in der Makrodefinition überein. Jeder formale Parameter in *-Token-Zeichenfolge* vorangestellt, ist kein Zeichenfolgenoperator (`#`), zeichenoperator (`#@`), oder Einfügen eines Tokens (`##`)-Operator, oder nicht, gefolgt von einer `##` ist Operator durch das entsprechende tatsächliche Argument ersetzt. Alle Makros im tatsächlichen Argument werden erweitert, bevor die Anweisung den formalen Parameter ersetzt. (Die Operatoren werden in beschrieben [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md).)

Die folgenden Beispiele von Makros mit Argumenten veranschaulichen das zweite Formular von der **#define** Syntax:

```C
// Macro to define cursor lines
#define CURSOR(top, bottom) (((top) << 8) | (bottom))

// Macro to get a random integer with a specified range
#define getrandom(min, max) \
    ((rand()%(int)(((max) + 1)-(min)))+ (min))
```

Argumente mit Nebeneffekten können dazu führen, dass Makros unerwartete Ergebnisse erzeugen. Ein angegebener formaler Parameter möglicherweise mehr als einmal in *-Token-Zeichenfolge*. Wenn der formale Parameter durch einen Ausdruck mit Nebeneffekten ersetzt wird, dann wird der Ausdruck samt seinen Nebeneffekten evtl. mehrmals ausgewertet. (Finden Sie unter den Beispielen unter [Tokeneinfügenden Operator (##)](../preprocessor/token-pasting-operator-hash-hash.md).)

Die `#undef`-Anweisung führt dazu, dass die Präprozessordefinition eines Bezeichners übergangen wird. Finden Sie unter [#undef-Direktive](../preprocessor/hash-undef-directive-c-cpp.md) für Weitere Informationen.

Bei der Namen des definierten Makros in *-Token-Zeichenfolge* (auch als Ergebnis einer anderen makroerweiterung), wird er nicht erweitert.

Ein zweites **#define** für ein Makro mit dem gleichen Namen eine Warnung generiert, es sei denn, die zweite tokensequenz mit dem ersten identisch ist.

**Microsoft-spezifisch**

Mit Microsoft C/C++ können Sie ein Makro neu definieren, wenn die neue Definition mit der ursprünglichen Definition syntaktisch identisch ist. Das bedeutet, dass die beiden Definitionen über unterschiedliche Parameternamen verfügen können. Dieses Verhalten unterscheidet sich von ANSI-C, die erfordert, dass die beiden Definitionen lexikalisch gleich sind.

Beispielsweise sind die folgenden beiden Makros identisch, abgesehen von den Parameternamen. ANSI C lässt keine solche Neudefinition zu, aber Microsoft C/C++-wird ohne Fehler kompiliert.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( a1 * a2 )
```

Andererseits sind die folgenden beiden Makros nicht identisch und generieren in Microsoft C/C++ eine Warnung.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( b1 * b2 )
```

**Ende Microsoft-spezifisch**

Dieses Beispiel veranschaulicht die **#define** Richtlinie:

```C
#define WIDTH       80
#define LENGTH      ( WIDTH + 10 )
```

Die erste Anweisung definiert den Bezeichner `WIDTH` als die ganzzahlige Konstante 80 und definiert `LENGTH` hinsichtlich `WIDTH` und der ganzzahligen Konstante 10. Jedes Vorkommen von `LENGTH` wird ersetzt durch (`WIDTH + 10`). Im Gegenzug wird jedes Vorkommen von `WIDTH + 10` durch den Ausdruck (`80 + 10`) ersetzt. Die Klammern um `WIDTH + 10` sind wichtig, da sie die Interpretation in Anweisungen steuern, z. B.:

```C
var = LENGTH * 20;
```

Nach der Vorverarbeitungsphase wird die Anweisung:

```C
var = ( 80 + 10 ) * 20;
```

zu 1800 ausgewertet. Ohne Klammern wird das Ergebnis:

```C
var = 80 + 10 * 20;
```

die 280 ergibt.

**Microsoft-spezifisch**

Definieren von Makros und Konstanten mit dem [/d](../build/reference/d-preprocessor-definitions.md) Compiler-Option hat dieselbe Wirkung wie die Verwendung einer **#define** -präprozessanweisung am Anfang der Datei. Maximal 30 Makros können mit der /D-Option definiert werden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)