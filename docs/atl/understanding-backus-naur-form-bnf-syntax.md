---
title: ATL-Registrar und BNF-Syntax (Backus-Naur-Form)
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 77f0fa6fef8e517e5714d1da6c61d0e310e0718c
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65709180"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Einführung in die BNF-Syntax (Backus-Naur-Form)

Die vom ATL-Registrar verwendeten Skripts sind in diesem Thema mit der BNF-Syntax beschrieben, für die die in der folgenden Tabelle aufgeführte Notation verwendet wird.

|Konvention/Symbol|Bedeutung|
|------------------------|-------------|
|::=|Entsprechung|
|&#124;|ODER|
|X+|Mindestens ein X.|
|\[X]|X ist optional. Optionale Trennzeichen sind durch \[] gekennzeichnet.|
|Jeglicher **fett** ausgezeichnete Text|Ein Zeichenfolgenliteral.|
|Jeglicher *kursiv* ausgezeichnete Text|Art und Weise, wie das Zeichenfolgenliteral erstellt wird.|

Wie in der obigen Tabelle angegeben ist, werden für Registrar-Skripts Zeichenfolgenliterale verwendet. Diese Werte sind tatsächlich Text, der in Ihrem Skript vorhanden muss. In der folgende Tabelle sind die Zeichenfolgenliterale beschrieben, die in einem ATL-Registrar-Skript verwendet werden.

|Zeichenfolgenliteral|Aktion|
|--------------------|------------|
|**ForceRemove**|Entfernt den nächsten Schlüssel (sofern vorhanden) vollständig und erstellt diesen dann neu.|
|**NoRemove**|Entfernt den nächsten Schlüssel beim Aufheben der Registrierung nicht.|
|**val**|Gibt an, dass `<Key Name>` tatsächlich ein benannter Wert ist.|
|**Delete**|Löscht den nächsten Schlüssel während der Registrierung.|
|**s**|Gibt an, dass der nächste Wert eine Zeichenfolge (REG_SZ) ist.|
|**d**|Gibt an, dass der nächste Wert ein DWORD-Wert (REG_DWORD) ist.|
|**m**|Gibt an, dass der nächste Wert eine mehrteilige Zeichenfolge (REG_MULTI_SZ) ist.|
|**b**|Gibt an, dass der nächste Wert ein Binärwert (REG_BINARY) ist.|

## <a name="bnf-syntax-examples"></a>Beispiele für die BNF-Syntax

Es folgen einige Syntaxbeispiele, die Ihnen verdeutlichen sollen, wie die Notation und die Zeichenfolgenliterale in einem ATL-Registrar-Skript funktionieren.

### <a name="syntax-example-1"></a>Syntaxbeispiel 1

```
<registry expression> ::= <Add Key>
```

gibt an, dass `registry expression` mit `Add Key` identisch ist.

### <a name="syntax-example-2"></a>Syntaxbeispiel 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

gibt an, dass `registry expression` entweder mit `Add Key` oder mit `Delete Key` identisch ist.

### <a name="syntax-example-3"></a>Syntaxbeispiel 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

gibt an, dass `Key Name` mit mindestens einem `AlphaNumerics`-Wert identisch ist.

### <a name="syntax-example-4"></a>Syntaxbeispiel 4

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

gibt an, dass `Add Key` mit `Key Name` identisch ist, und dass die Zeichenfolgenliterale `ForceRemove`, `NoRemove` und `val` optional sind.

### <a name="syntax-example-5"></a>Syntaxbeispiel 5

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

gibt an, dass `AlphaNumeric` mit jedem Nicht-NULL-Zeichen identisch ist.

### <a name="syntax-example-6"></a>Syntaxbeispiel 6

```
val 'testmulti' = m 'String 1\0String 2\0'
```

gibt an, dass der Schlüsselname `testmulti` eine mehrteilige Zeichenfolge ist, die aus `String 1` und `String 2` besteht.

### <a name="syntax-example-7"></a>Syntaxbeispiel 7

```
val 'testhex' = d '&H55'
```

gibt an, dass der Schlüsselname `testhex` ein DWORD-Wert ist, der auf hexadezimal 55 (dezimal 85) festgelegt ist. Beachten Sie, dass dieses Format der **&H**-Notation entspricht, wie sie in der Visual Basic-Spezifikation enthalten ist.

## <a name="see-also"></a>Siehe auch

[Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)
