---
title: Symbolwerten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.value
dev_langs:
- C++
helpviewer_keywords:
- symbols, value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ed1631d9b8f0c591006c7b708662b3a7321f22b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602743"
---
# <a name="symbol-value-restrictions"></a>Beschränkungen bei Symbolwerten

Bei einem Symbolwert kann es sich um eine beliebige Ganzzahl handeln, die in normaler Form für „#define preprocessor“-Anweisungen ausgedrückt wird. Hier sind einige Beispiele für Symbolwerte:

```
18
4001
0x0012
-3456
```

Bei Symbolwerten für Ressourcen (Zugriffstaste, Bitmaps, Cursor, Dialogfelder, Symbole, Menüs, Zeichenfolgentabellen und Versionsinformationen) muss es sich um Dezimalzahlen im Bereich von 0 bis 32.767 handeln (darf nicht hexadezimal sein). Symbolwerte für Ressourcenbestandteile wie Dialogfeldsteuerelemente oder einzelne Zeichenfolgen in der Zeichenfolgentabelle können von 0 bis 65.534 oder von -32.768 bis 32.767 reichen.

Bei Ressourcensymbolen handelt es sich um 16-Bit-Zahlen. Sie können sie signiert oder nicht signiert eingeben. Sie werden jedoch intern als nicht signierte Ganzzahlen verwendet. Negative Zahlen werden demnach in ihre entsprechenden positiven Werte umgewandelt.

Im Folgenden finden Sie einige Beschränkungen für Symbolwerte:

- Die Visual Studio-Entwicklungsumgebung und MFC verwenden einige Zahlenbereiche für besondere Zwecke. Alle Zahlen mit dem wichtigsten Bitset (-32.768 bis -1 oder 32.768 bis 65.534 in Abhängigkeit des Zeichens) sind für MFC reserviert.

- Es ist nicht möglich, einen Symbolwert mithilfe von anderen Symbolzeichenfolgen zu definieren. Beispielsweise wird die folgende Symboldefinition nicht unterstützt:

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- Sie können Präprozessormakros mit Argumenten nicht als Wertdefinitionen verwenden. Zum Beispiel:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   Ist kein gültiger Ausdruck, unabhängig davon, was `ID` zum Zeitpunkt der Kompilierung auswertet.

- Ihre Anwendung verfügt möglicherweise über eine vorhandene Datei, die mit Ausdrücken definierte Symbole enthält. Weitere Informationen zum Einschließen der Symbole als schreibgeschützte Symbole finden Sie unter [gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).

Weitere Informationen über Zahlenbereiche finden Sie unter [TN023: MFC-Standardressourcen](../mfc/tn023-standard-mfc-resources.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ändern des numerischen Werts eines Symbols](../windows/changing-a-symbol-s-numeric-value.md)  
[Beschränkungen bei Symbolnamen](../windows/symbol-name-restrictions.md)  
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)