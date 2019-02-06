---
title: Ändern eines Symbols
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
- symbols [C++], value restrictions
- restrictions, symbol values
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 7d2890c2d2c05f1ee0309446dfe2de9917f85707
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763985"
---
# <a name="changing-a-symbol"></a>Ändern eines Symbols

Wenn Sie eine neue Ressource oder ein Ressourcenobjekt erstellen, weist die Entwicklungsumgebung einen standardmäßigen Symbolnamen zu, beispielsweise IDD_DIALOG1. Sie können die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) um den standardmäßigen Symbolnamen zu ändern oder den Namen eines beliebigen bereits mit einer Ressource verknüpften Symbols zu ändern.

Symbole, die eine einzelne Ressource zugeordnet werden, können Sie auch die **Eigenschaften** um den Symbolwert zu ändern. Können Sie die [Dialogfeld Ressourcensymbole](../windows/resource-symbols-dialog-box.md) so ändern Sie den Wert von Symbolen, die derzeit nicht auf eine Ressource zugewiesen. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).

Normalerweise alle Symboldefinitionen, die in gespeichert werden `Resource.h`. Jedoch müssen Sie den Namen dieser Includedatei möglicherweise ändern, sodass Sie z. B. mit mehr als eine Ressourcendatei im selben Verzeichnis arbeiten können.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="to-change-a-resources-symbol-name-id"></a>Ändern einer Ressource (Symbolnamens (ID)

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der **Eigenschaften** Fenster, geben Sie einen neuen Symbolnamen ein, oder wählen Sie aus der Liste der vorhandenen Symbole im der **ID** Feld.

   Wenn Sie einen neuen Symbolnamen eingeben, wird diesem automatisch ein Wert zugewiesen.

Sie können die [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md) so ändern Sie die Namen der derzeit nicht auf eine Ressource zugewiesenen Symbole. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).

### <a name="symbol-name-restrictions"></a>Beschränkungen bei Symbolnamen

Die Einschränkungen für Symbolnamen lauten wie folgt:

- Alle [Symbole](../windows/symbols-resource-identifiers.md) muss innerhalb des Bereichs der Anwendung eindeutig sein. Dadurch werden Symboldefinitionskonflikte in den Headerdateien verhindert.

- Zu den gültigen Zeichen für einen Symbolnamen zählen A–Z, a–z, 0–9 und Unterstriche ( – ).

- Symbolnamen dürfen nicht mit einer Zahl beginnen und sind auf 247 Zeichen begrenzt.

- Symbolnamen dürfen keine Leerzeichen enthalten.

- Bei Symbolnamen wird die Groß-/Kleinschreibung nicht beachtet. Die Groß-/Kleinschreibung der ersten Symboldefinition wird jedoch beibehalten. Die die Symbole definierende Headerdatei wird durch den Ressourcencompiler/Editor und durch das bzw. die C++Programm(e) verwendet, um auf in einer Ressourcendatei definierte Ressourcen zu verweisen. Bei zwei Symbolnamen, die sich nur in der Groß-/Kleinschreibung unterscheiden, erkennt das C++-Programm zwei getrennte Symbole, während der Ressourcencompiler/Editor beide Namen als ein einzelnes Symbol erkennt.

   > [!NOTE]
   > Wenn Sie das im Folgenden hervorgehobene standardmäßige Symbolnamensschema (ID*_[keyword]) nicht befolgen und Ihr Symbolname dem Schlüsselwort entspricht, das dem Ressourcenskriptcompiler bekannt ist, führt der Versuch, die Ressourcenskriptdatei zu erstellen, anscheinend zu einer zufälligen Fehlergenerierung, die sich schwer diagnostizieren lässt. Halten Sie sich an die standardmäßige Namensgebung, um dies zu verhindern.

Symbolnamen weisen beschreibende Präfixe auf, die die Art der Ressource oder des Objekts andeuten, die bzw. das sie repräsentieren. Diese beschreibenden Präfixe beginnen mit der Textkombinations-ID. Die Microsoft Foundation Class-Bibliothek (MFC) verwendet die in der folgenden Tabelle gezeigten Symbolnamenskonventionen.

|Kategorie|Präfix|Mit|
|--------------|------------|---------|
|Ressourcen|IDR_ IDD_ IDC_ IDI_ IDB_|Zugriffstaste oder Menü (sowie zugehörige oder benutzerdefinierte Ressourcen), Dialogfeld, Cursor, Symbol, Bitmap|
|Menüelemente|ID_|Menüelement|
|Befehle|ID_|Befehl|
|Steuerelemente und untergeordnete Fenster|IDC_|Steuerelement|
|Zeichenfolgen|IDS_|Zeichenfolge in der Zeichenfolgentabelle|
|MFC|AFX_|Reserviert für vordefinierte MFC-Symbole|

## <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>So ändern Sie einen zu einer einzelnen Ressource oder einem Objekt zugewiesenen Symbolwert

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der **Eigenschaften** geben den Symbolnamen, gefolgt von einem Gleichheitszeichen und einer ganzen Zahl in die **ID** Feld, z. B.:

    ```
    IDC_EDITNAME=5100
    ```

Der neue Wert wird in der Symbolheaderdatei gespeichert, wenn Sie das nächste Mal das Projekt speichern. Nur der Symbolnamen verbleibt weiterhin im Feld „ID“ sichtbar. Nach der Überprüfung werden das Gleichheitszeichen und der Wert nicht mehr angezeigt.

### <a name="symbol-value-restrictions"></a>Beschränkungen für Symbolwerte

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

## <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>So ändern Sie den Namen den Symbolheaderdatei für die Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der **Symbolheaderdatei** geben den neuen Namen für die Include-Datei.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)<br/>
[Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)<br/>
