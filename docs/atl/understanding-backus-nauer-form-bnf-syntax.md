---
title: ATL-Registrierung und Backus Nauer Form (BNF)-Syntax
ms.date: 11/04/2016
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 0b48e0b4abc8601b5173c3c7d2748c726646fbc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196461"
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>Grundlegendes zu Backus Nauer Form (BNF)-Syntax

Die Skripts, die von der ATL-Registrierung verwendet werden beschrieben, in diesem Thema mithilfe der BNF-Syntax, die in der folgenden Tabelle aufgeführten Notation verwendet wird.

|Konvention/symbol|Bedeutung|
|------------------------|-------------|
|::=|Entsprechung|
|&#124;|ODER|
|X+|Eine oder mehrere Xs.|
|[X]|X ist optional. Optionale Trennzeichen sind gekennzeichnet durch \[].|
|Alle **fett** Text|Ein Zeichenfolgenliteral.|
|Alle *Kursiv* Text|So erstellen Sie das Zeichenfolgenliteral.|

Wie in der obigen Tabelle angegeben wird, verwenden Sie registrierungsskripte Zeichenfolgenliterale. Diese Werte sind die eigentliche Text, der im Skript verwendet werden muss. In der folgende Tabelle wird beschrieben, die Zeichenfolgenliterale in einem ATL-Registrierung-Skript verwendet wird.

|Zeichenfolgenliteral|Aktion|
|--------------------|------------|
|**ForceRemove**|Mit der nächste Taste vollständig entfernt werden, (falls vorhanden) und dann neu erstellt.|
|**NoRemove**|Mit der nächste Taste werden nicht während der Aufhebung der Registrierung entfernt werden.|
|**val**|Gibt an, dass `<Key Name>` ist tatsächlich ein benannter Wert.|
|**Löschen**|Löscht den nächsten Schlüssel während der Registrierung.|
|**s**|Gibt an, dass der nächste Wert eine Zeichenfolge (REG_SZ).|
|**d**|Gibt an, dass der nächste Wert ein DWORD (REG_DWORD).|
|**m**|Gibt an, dass der nächste Wert eine mehrteilige Zeichenfolge (REG_MULTI_SZ).|
|**b**|Gibt an, dass der nächste Wert einen Binärwert (REG_BINARY).|

## <a name="bnf-syntax-examples"></a>Beispiele für die BNF-Syntax

Hier sind einige Beispiele für Abfragesyntax um besser zu verstehen, wie die Literale Notation und die Zeichenfolge in einem ATL-Registrierung Skript funktionieren.

### <a name="syntax-example-1"></a>Attributsyntax-Beispiel 1

```
<registry expression> ::= <Add Key>
```

Gibt an, dass `registry expression` entspricht `Add Key`.

### <a name="syntax-example-2"></a>Attributsyntax-Beispiel 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

Gibt an, dass `registry expression` entspricht entweder `Add Key` oder `Delete Key`.

### <a name="syntax-example-3"></a>Syntaxbeispiel 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

Gibt an, dass `Key Name` entspricht einer oder mehreren `AlphaNumerics`.

### <a name="syntax-example-4"></a>Syntaxbeispiel 4

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

Gibt an, dass `Add Key` entspricht `Key Name`, und dass die Zeichenfolgenliterale `ForceRemove`, `NoRemove`, und `val`, sind optional.

### <a name="syntax-example-5"></a>Syntaxbeispiel 5

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

Gibt an, dass `AlphaNumeric` entspricht, alle nicht-NULL-Zeichen.

### <a name="syntax-example-6"></a>Attributsyntax-Beispiel 6

```
val 'testmulti' = m 'String 1\0String 2\0'
```

Gibt an, dass der Schlüsselname `testmulti` eine mehrteilige Zeichenfolge besteht aus `String 1` und `String 2`.

### <a name="syntax-example-7"></a>Syntaxbeispiel 7

```
val 'testhex' = d '&H55'
```

Gibt an, dass der Schlüsselname `testhex` ist ein DWORD-Wert, die auf hexadezimale 55 (decimal 85) festgelegt. Beachten Sie dieses Format entspricht dem **& H** Notation als finden Sie in der Visual Basic-Spezifikation.

## <a name="see-also"></a>Siehe auch

[Erstellen von Registrierungsskripts](../atl/creating-registrar-scripts.md)
