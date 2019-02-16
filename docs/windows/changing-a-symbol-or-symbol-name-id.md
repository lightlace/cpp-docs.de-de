---
title: 'Vorgehensweise: Verwaltung von Symbolen'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
- vc.editors.symbol.changing.unassigned
- vc.editors.symbol.shared.calculated
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
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 4f1c44e8fc2ae34ddcb65ec23ca8d98e11d50ec0
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320587"
---
# <a name="how-to-manage-symbols"></a>Vorgehensweise: Verwaltung von Symbolen

Wenn Sie eine neue Ressource oder ein Ressourcenobjekt erstellen, weist die Entwicklungsumgebung einen standardmäßigen Symbolnamen zu, beispielsweise IDD_DIALOG1. Sie können die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) um den standardmäßigen Symbolnamen zu ändern oder den Namen eines beliebigen bereits mit einer Ressource verknüpften Symbols zu ändern.

Symbole, die eine einzelne Ressource zugeordnet werden, können Sie auch die **Eigenschaften** um den Symbolwert zu ändern. Können Sie die [Dialogfeld Ressourcensymbole](../windows/resource-symbols-dialog-box.md) so ändern Sie den Wert von Symbolen, die derzeit nicht auf eine Ressource zugewiesen.

Normalerweise alle Symboldefinitionen, die in gespeichert werden `Resource.h`. Jedoch müssen Sie den Namen dieser Includedatei möglicherweise ändern, sodass Sie z. B. mit mehr als eine Ressourcendatei im selben Verzeichnis arbeiten können.

> [!NOTE]
> Wenn Ihr Projekt noch keine RC-Datei enthält, finden Sie unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

## <a name="symbol-name-restrictions"></a>Beschränkungen bei Symbolnamen

Die Einschränkungen für Symbolnamen lauten wie folgt:

- Alle [Symbole](../windows/symbols-resource-identifiers.md) muss innerhalb des Bereichs der Anwendung eindeutig sein. Dadurch werden Symboldefinitionskonflikte in den Headerdateien verhindert.

- Zu den gültigen Zeichen für einen Symbolnamen zählen A–Z, a–z, 0–9 und Unterstriche ( – ).

- Symbolnamen dürfen nicht mit einer Zahl beginnen und sind auf 247 Zeichen begrenzt.

- Symbolnamen dürfen enthalten keine Leerzeichen.

- Symbolnamen dürfen nicht beachtet die Groß-/Kleinschreibung der ersten Symboldefinition wird jedoch beibehalten. Die die Symbole definierende Headerdatei wird durch den Ressourcencompiler/Editor und durch das bzw. die C++Programm(e) verwendet, um auf in einer Ressourcendatei definierte Ressourcen zu verweisen. Bei zwei Symbolnamen, die sich nur in der Groß-/Kleinschreibung unterscheiden, erkennt das C++-Programm zwei getrennte Symbole, während der Ressourcencompiler/Editor beide Namen als ein einzelnes Symbol erkennt.

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

### <a name="to-change-a-symbol-name-id"></a>So ändern Sie eine Symbolnamens (ID)

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

1. In der **Eigenschaften** Fenster, geben Sie einen neuen Symbolnamen ein, oder wählen Sie aus der Liste der vorhandenen Symbole im der **ID** Feld.

   Wenn Sie einen neuen Symbolnamen eingeben, ist er automatisch einen Wert zugewiesen.

Sie können die [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md) so ändern Sie die Namen der derzeit nicht auf eine Ressource zugewiesenen Symbole.

## <a name="symbol-value-restrictions"></a>Beschränkungen bei Symbolwerten

Bei einem Symbolwert kann es sich um eine beliebige Ganzzahl handeln, die in normaler Form für „#define preprocessor“-Anweisungen ausgedrückt wird. Hier sind einige Beispiele für Symbolwerte:

```
18
4001
0x0012
-3456
```

Bei Symbolwerten für Ressourcen (Zugriffstaste, Bitmaps, Cursor, Dialogfelder, Symbole, Menüs, Zeichenfolgentabellen und Versionsinformationen) muss es sich um Dezimalzahlen im Bereich von 0 bis 32.767 handeln (darf nicht hexadezimal sein). Symbolwerte für Ressourcenbestandteile wie Dialogfeldsteuerelemente oder einzelne Zeichenfolgen in der Zeichenfolgentabelle können von 0 bis 65.534 oder von -32.768 bis 32.767 reichen.

Bei Ressourcensymbolen handelt es sich um 16-Bit-Zahlen. Sie können sie eingeben, mit oder ohne Vorzeichen, aber sie werden verwendet intern als Ganzzahlen ohne Vorzeichen. Negative Zahlen werden demnach in ihre entsprechenden positiven Werte umgewandelt.

Im Folgenden finden Sie einige Beschränkungen für Symbolwerte:

- Die Visual Studio-Entwicklungsumgebung und MFC verwenden einige Zahlenbereiche für besondere Zwecke. Alle Zahlen mit dem wichtigsten Bitset (-32.768 bis -1 oder 32.768 bis 65.534 in Abhängigkeit des Zeichens) sind für MFC reserviert.

- Sie können keinen Symbolwert mithilfe von anderen Symbolzeichenfolgen definieren. Beispielsweise wird die folgende Symboldefinition nicht unterstützt:

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- Sie können nicht als Wertdefinitionen Präprozessormakros mit Argumenten verwenden. Zum Beispiel:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   ist nicht unabhängig davon, was ein gültiger Ausdruck `ID` zum Zeitpunkt der Kompilierung ergibt.

- Ihre Anwendung verfügt möglicherweise über eine vorhandene Datei, die mit Ausdrücken definierte Symbole enthält. Weitere Informationen zum Einschließen der Symbole als schreibgeschützte Symbole finden Sie unter [gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).

Weitere Informationen über Zahlenbereiche finden Sie unter [TN023: MFC-Standardressourcen](../mfc/tn023-standard-mfc-resources.md).

### <a name="to-change-a-symbol-value"></a>So ändern Sie den Wert eines Symbols

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

1. In der **Eigenschaften** geben den Symbolnamen, gefolgt von einem Gleichheitszeichen und einer ganzen Zahl in die **ID** Feld, z. B.:

    ```
    IDC_EDITNAME=5100
    ```

Der neue Wert wird in der Symbolheaderdatei gespeichert, wenn Sie das nächste Mal das Projekt speichern. Nur der Symbolnamen verbleibt weiterhin angezeigt, in das Feld-ID; Das Gleichheitszeichen und Wert werden nicht angezeigt, nachdem sie überprüft haben.

## <a name="change-or-delete-symbols"></a>Ändern oder Löschen von Symbolen

Während Sie sich in der [Ressourcensymbole (Dialogfeld)](../windows/resource-symbols-dialog-box.md), können Sie bearbeiten oder löschen Sie vorhandene Symbole, die bereits auf eine Ressource oder das Objekt zugewiesen wird.

### <a name="to-change-an-unassigned-symbol"></a>So ändern Sie ein nicht zugewiesenes Symbol

1. In der **Namen** Feld, das nicht zugewiesene Symbol auswählen, und wählen **Änderung**.

1. Bearbeiten des Symbols oder -Wert in den angezeigten Feldern der **Symbol ändern** Dialogfeld.

   > [!NOTE]
   > So ändern Sie ein Symbol, *ist* , eine Ressource oder einem Objekt zugewiesen wird, müssen Sie den Ressourcen-Editor verwenden oder **Eigenschaften** Fenster.

### <a name="to-delete-an-unassigned-unused-symbol"></a>So löschen Sie ein nicht zugewiesenes (nicht verwendetes) Symbol

In der [Dialogfeld Ressourcensymbole](../windows/resource-symbols-dialog-box.md), wählen Sie das Symbol, das Sie verwenden möchten, löschen, und wählen Sie **löschen**.

   > [!NOTE]
   > Stellen Sie vor dem Löschen eines nicht verwendeten Symbols in einer Ressourcendatei sicher, dass es nicht an anderer Stelle im Programm oder durch die Ressourcendateien zum Zeitpunkt der Kompilierung verwendet wird.

## <a name="include-symbols"></a>Symbole einschließen

Wenn die Entwicklungsumgebung erstmals eine durch eine andere Anwendung erstellte Ressourcendatei liest, markiert sie alle einbezogenen Headerdateien als schreibgeschützt. Dennoch können Sie Sie verwenden die [Dialogfeld Ressourcenincludes](../windows/resource-includes-dialog-box.md) um zusätzliche schreibgeschützte Symbolheaderdateien hinzuzufügen.

Ein Grund, weshalb Sie möglicherweise schreibgeschützte Symboldefinitionen verwenden möchten, ist der Plan, Symboldateien unter verschiedenen Projekten freizugeben.

Sie können zudem einbezogene Symboldateien verwenden, wenn Sie über vorhandene Ressourcen mit Symboldefinitionen verfügen, die anstelle von einfachen Ganzzahlen Ausdrücke zum Definieren des Symbolwerts verwenden. Zum Beispiel:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)
```

Die Umgebung interpretiert diese berechneten Symbole ordnungsgemäß, sofern Folgendes gegeben ist:

- Die berechneten Symbole sind in einer schreibgeschützten Symboldatei platziert.

- Ihre Ressourcendatei enthält Ressourcen, zu denen diese berechneten Symbole bereits zugewiesen sind.

- Es wird ein numerischer Ausdruck erwartet.

> [!NOTE]
> Wenn eine Zeichenfolge oder ein numerischer Ausdruck erwartet wird, wird der Ausdruck nicht ausgewertet.

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>So beziehen Sie freigegebene (schreibgeschützte) Symbole in Ihrer Ressourcendatei ein

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.

1. In der **Anweisungen für schreibgeschützte Symbole** können Sie über die `#include` Compilerdirektive, um die Datei angeben, werden die schreibgeschützten Symbole beibehalten werden soll.

   Rufen Sie die Datei nicht `Resource.h`, da dies der Dateiname, der normalerweise durch die Hauptsymbol-Headerdatei ist.

   > [!NOTE]
   > **Wichtige** Eingabe im Feld Direktiven für schreibgeschützte Symbole in der Ressourcendatei enthalten ist, genau, wie Sie es eingeben. Stellen Sie sicher, dass die Eingabe weder Schreib- noch Syntaxfehler aufweist.

   Verwenden der **Anweisungen für schreibgeschützte Symbole** Kontrollkästchen, um Dateien mit Symboldefinitionen nur einzubeziehen. Ressourcendefinitionen Sie keine; Andernfalls werden doppelte Ressourcendefinitionen erstellt werden, wenn die Datei gespeichert wird.

1. Platzieren Sie die Symbole in der von Ihnen angegebenen Datei.

   Die Symbole in die Dateien einbezogenen auf diese Weise werden jedes Mal, die Sie Ihre Ressourcendatei öffnen, aber sie sind nicht auf dem Datenträger ersetzt, wenn Sie die Datei speichern.

1. Klicken Sie auf **OK**.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>So ändern Sie den Namen den Symbolheaderdatei für die Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.

1. In der **Symbolheaderdatei** geben den neuen Namen für die Include-Datei.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-IDs (Symbole)](../windows/symbols-resource-identifiers.md)<br/>
[Erstellen von Symbolen](../windows/creating-new-symbols.md)<br/>
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)<br/>