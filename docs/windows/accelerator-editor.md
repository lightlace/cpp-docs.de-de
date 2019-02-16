---
title: Zugriffstasten-Editor (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator.F1
- vc.editors.accelerator
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
- VIRTKEY
- Key property
- ID property
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
- searching, in accelarator tables
- accelerator tables [C++], finding entries
- accelerator tables [C++], adding entries
- New Accelerator command
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
- accelerator tables [C++], copying entries
- rc files [C++], moving an accelerator table entry
- .rc files [C++], moving accelerator table entries
- accelerator tables [C++], moving entries
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: 90ef142336cf88c5e40f78f6cc651b2bb35a0f6c
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320639"
---
# <a name="accelerator-editor-c"></a>Zugriffstasten-Editor (C++)

Eine Zugriffstastentabelle ist eine C++-Windows-Ressource, die eine Liste mit Zugriffstasten (auch als Tastenkombinationen bezeichnet) enthält und die Befehls-IDs, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.

Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.

Sie können die [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) verwenden, um Zugriffstastenbefehle mit Code zu verknüpfen.

Eine Liste der vordefinierten Zugriffstasten, finden Sie unter [vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md).

   > [!TIP]
   > Bei der Verwendung der **Accelerator** -Editor, Sie können mit der rechten Maustaste ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.

   > [!NOTE]
   > Windows lässt die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.

## <a name="accelerator-properties"></a>Eigenschaften für Zugriffstasten

Sie können die Eigenschaften für Zugriffstasten festlegen, der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können auch die **Accelerator** -Editor, um die tastenkombinationseigenschaften in der tastenkombinationstabelle zu ändern. Änderungen, die mit der **Eigenschaften** Fenster oder der **Accelerator** Editor aufweisen, das gleiche Ergebnis: Änderungen werden sofort in der tastenkombinationstabelle dargestellt.

### <a name="id-property"></a>ID-Eigenschaft

Die **ID** -Eigenschaft verweist auf die einzelnen Einträge im Programmcode Accelerator. Dieser Eintrag ist der Befehlswert, den das Programm erhalten sollen, wenn ein Benutzer die Zugriffstaste oder Tastenkombination drückt. Um einer Zugriffstaste identisch mit der ein Menüelement zu machen, müssen Sie deren IDs identisch (sofern die ID der Tabelle mit Zugriffstasten wird die die ID für die Menüressource identisch ist).

Es gibt drei Eigenschaften für jede ID der Zugriffstaste: die **Modifizierer** -Eigenschaft, die **Schlüssel** -Eigenschaft, und die **Typ** Eigenschaft.

#### <a name="modifier-property"></a>Modifier-Eigenschaft

Die **Modifizierer** Eigenschaftensätze Steuerelement Tastenkombinationen für die Zugriffstaste.

> [!NOTE]
> In der **Eigenschaften** Fenster, diese Eigenschaft wird als drei Separate **booleschen** Eigenschaften, die alle davon unabhängig gesteuert werden können: **ALT**, **STRG**, und **UMSCHALT**.

Die folgende sind zulässige Einträge für die **Modifizierer** Eigenschaft in der tastenkombinationstabelle:

   |Wert|Beschreibung|
   |-----------|-----------------|
   |**Keine**|Benutzer drückt nur die **Schlüssel** Wert. Dieser Wert ist am effizientesten mit den ASCII/ANSI-Werten 001 bis 026, was interpretiert wird als ^ A bis ^ Z (**STRG + A** über **STRG + Z**).|
   |**ALT**|Drücken Sie die Benutzer muss die **Alt** Schlüssel vor der **Schlüssel** Wert.|
   |**STRG**|Drücken Sie die Benutzer muss die **STRG** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|
   |**UMSCHALTTASTE**|Drücken Sie die Benutzer muss die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert.|
   |**Strg + Alt +**|Drücken Sie die Benutzer muss die **STRG** Schlüssel und die **Alt** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|
   |**STRG + UMSCHALT**|Drücken Sie die Benutzer muss die **STRG** Schlüssel und die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|
   |**ALT + UMSCHALT**|Drücken Sie die Benutzer muss die **Alt** Schlüssel und die **UMSCHALT** Schlüssel vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|
   |**Strg + Alt + Umschalt**|Der Benutzer muss drücken **STRG**, **Alt**, und **UMSCHALT** vor der **Schlüssel** Wert. Mit dem ASCII-Typ nicht gültig.|

#### <a name="key-property"></a>Key-Eigenschaft

Die **Schlüssel** Eigenschaft legt fest, den tatsächlichen Schlüssel als Zugriffstaste verwenden.

Die folgende sind zulässige Einträge für die **Schlüssel** Eigenschaft in der tastenkombinationstabelle:

   |Wert|Beschreibung|
   |-----------|-----------------|
   |Eine ganze Zahl zwischen 0 und 255 im Dezimalformat.|Der Wert bestimmt, ob der Wert als ASCII oder ANSI, wie folgt behandelt wird:<br/><br/>-Einstellige Zahlen werden immer als der entsprechende Schlüssel und nicht als ASCII oder ANSI-Werte interpretiert.<br/>-Werte von 1 bis 26, wenn Nullen vorangestellt werden als interpretiert ^ A bis ^ Z, steht für den ASCII-Wert, der den Buchstaben des Alphabets, wenn Sie mit gedrückt der **STRG** -Taste gedrückt gehalten.<br/>-Werte von 27-32 werden immer als drei Ziffern bestehenden Dezimalwerte 027 bis 032 interpretiert.<br/>-Werte von 033 bis 255, 0 vorangestellt oder nicht als ANSI-Werte interpretiert werden.|
   |Ein einzelnes Zeichen der Tastatur.|Großbuchstaben von A - Z oder die Ziffern 0 – 9 können entweder ASCII- oder den virtuellen Schlüsselwerte; Alle anderen Zeichen ist ASCII nur an.|
   |Ein einzelnes Zeichen der Tastatur im Bereich von A - Z (nur Großbuchstaben), ein Caretzeichen (^) vorangestellt (z. B. ^ C).|Diese Option gibt den ASCII-Wert des Schlüssels aus, wenn es gedrückt wird, mit der **STRG** -Taste gedrückt gehalten.|
   |Alle gültigen virtuellen Tastenbezeichner.|Die Dropdownliste im Feld in der tastenkombinationstabelle enthält eine Liste der standardmäßigen virtuellen Schlüsselbezeichner.|

> [!NOTE]
> Wenn Sie einen ASCII-Wert eingeben, sind die Modifizierer-Optionen beschränkt. Ist der einzige Steuerelement verfügbare Schlüssel für die Verwendung der **Alt** Schlüssel.

> [!TIP]
> Eine weitere Möglichkeit zum Definieren einer Zugriffstaste wird mit der rechten Maustaste einen oder mehrere Einträge in der Zugriffstastentabelle, wählen **Nächste Taste** aus dem Kontextmenü, und drücken Sie dann eine der Tasten bzw. Tastenkombinationen auf der Tastatur. Die **Nächste Taste** Befehl steht auch auf die **bearbeiten** Menü.

#### <a name="type-property"></a>Type-Eigenschaft

Die **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der ID der Zugriffstaste verknüpft ist als ein ASCII/ANSI-Schlüssel-Wert oder eine Kombination der Schlüssel für ein virtuelles (VIRTKEY) interpretiert wird.

- Wenn der **Typ** -Eigenschaft ist ASCII, die **Modifizierer** Eigenschaft ist möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste, die verwendet die **STRG** Schlüssel () angegeben, die den Schlüssel mit abgrenzen, indem Sie eine `^`).

- Wenn die **Typ** -Eigenschaft ist VIRTKEY, eine beliebige Kombination von `Modifier` und `Key` Werte gilt.

> [!NOTE]
> Wenn Sie verwenden möchten, geben einen Wert in die Zugriffstastentabelle, und den Wert als ASCII/ANSI, klicken Sie behandelt werden die **Typ** für den Eintrag in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** im Menü) an die `Key`, müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY ASCII *vor* eingeben der `Key` Code.

## <a name="accelerator-tables"></a>Zugriffstastentabellen

Sie können eine Zugriffstastentabelle in eine C++-Projekt bearbeiten, direkt mit der direkten Bearbeitung in der **Accelerator** Editor.

Die folgenden Verfahren beziehen sich auf die Verwendung von standard-Eigenschaftenseiten können jedoch die direkte Bearbeitung und der Seitenmethode für das gleiche Ergebnis. Änderungen mithilfe von Eigenschaftenseiten oder mithilfe der direkten Bearbeitung werden sofort in der tastenkombinationstabelle dargestellt.

### <a name="to-edit-in-an-accelerator-table"></a>So führen Sie die Bearbeitung in einer Zugriffstastentabelle durch

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie einen Eintrag in der Tabelle, und wählen Sie auf die um direkte Bearbeitung zu aktivieren.

1. Treffen Sie eine Auswahl im Dropdown-Kombinationsfeld, oder geben Sie diese direkt ein, um Änderungen vornehmen.

   - Für **ID**, wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für **Modifizierer**, wählen Sie aus der Liste.

   - Für **Schlüssel**, wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für **Typ**Option **ASCII** oder **VIRTKEY** aus der Liste.

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>So suchen Sie einen Eintrag in einer geöffneten Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie eine Spaltenüberschrift, um den Inhalt der Spalte alphabetisch zu sortieren. Wählen Sie z. B. **ID** , alle IDs, die in der Zugriffstastentabelle in alphabetischer Reihenfolge anzuzeigen.

Sie können die Liste dann durchsuchen und den gewünschten Eintrag finden.

### <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Mit der rechten Maustaste in die Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste** über das Kontextmenü, oder wählen Sie den Eintrag leere Zeile am unteren Rand der Tabelle.

1. Wählen Sie eine **ID** Feld aus der Dropdown-Liste in die ID, oder geben Sie eine neue ID in der **ID** Feld.

1. Typ der **Schlüssel** Sie verwenden möchten, verwenden Sie als eine Zugriffstaste oder eine mit der rechten Maustaste, und wählen **Nächste Taste** aus dem Kontextmenü aus, um eine Tastenkombination festzulegen (der **Nächste Taste** Befehl ist auch verfügbar in der **bearbeiten** Menü).

1. Ändern der **Modifizierer** und **Typ**, falls erforderlich.

1. Drücken Sie die **EINGABETASTE**.

   > [!NOTE]
   > Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Sie können mehrere Tastenkombinationen ohne weitere Auswirkungen, z. B. dieselbe ID zugewiesen haben **STRG** + **P** und **F8** "id_print" zugewiesen werden. Allerdings müssen Sie eine Tastenkombination zugewiesen mit ID nicht, z. B. funktioniert mehr als einem **STRG** + **Z** sowohl "ID_SPELL_CHECK" und "Dies zugewiesen.

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>So löschen Sie einen Eintrag aus einer Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie den zu löschenden Eintrag aus. (Halten Sie die **STRG** oder **UMSCHALT** gedrückt, während Sie auswählen, um mehrere Einträge auszuwählen.)

1. Mit der rechten Maustaste, und wählen Sie **löschen** aus dem Kontextmenü (oder wählen Sie **löschen** aus der **bearbeiten** Menü).

> [!TIP]
> Eine Verknüpfung zum Löschen ist, drücken die **löschen** Schlüssel.

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>So verschieben oder kopieren Sie einen Eintrag in einer Zugriffstastentabelle in eine andere Ressourcenskriptdatei

1. Öffnen Sie in beiden Ressourcenskriptdateien die Zugriffstastentabellen.

1. Markieren Sie den Eintrag, der verschoben werden soll.

1. Von der **bearbeiten** Menü wählen **Kopie** oder **Ausschneiden**.

1. Markieren Sie einen Eintrag in der Ziel-Ressourcenskriptdatei.

1. Von der **bearbeiten** Menü wählen **einfügen**.

   > [!NOTE]
   > Zum Kopieren und Einfügen können Sie auch Tastenkombinationen verwenden.

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Zum Ändern der Eigenschaften mehrerer Zugriffstasten

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie die Zugriffstasten, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie jede auswählen.

1. Wechseln Sie zu der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) , und geben Sie die Werte aller ausgewählten Zugriffstasten freigeben.

   > [!NOTE]
   > Jeder Modifiziererwert angezeigt wird, als eine boolesche Eigenschaft in der **Eigenschaften** Fenster. Wenn Sie ändern eine [Modifizierer](../windows/accelerator-modifier-property.md) Wert in der **Eigenschaften** Fenster die Zugriffstastentabelle behandelt den new-Modifizierer als eine Erweiterung für alle Modifizierer, die bereits vorhanden waren. Aus diesem Grund setzen Sie alle Modifiziererwerte, Sie benötigen, legen Sie alle Angaben, um sicherzustellen, dass alle Zugriffstasten dasselbe **Modifizierer** Einstellungen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)<br/>