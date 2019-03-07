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
ms.openlocfilehash: f57c09d549a4ceb92db21c06499b4f6e71fc6a52
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57562938"
---
# <a name="accelerator-editor-c"></a>Zugriffstasten-Editor (C++)

Eine Zugriffstastentabelle ist eine C++-Windows-Ressource, die enthält eine Liste mit Tastenkombinationen, bekannt als Tastenkombinationen und die Befehls-IDs, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.

Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.

> [!TIP]
> Bei Verwendung der **Zugriffstasten-Editor**, mit der rechten Maustaste ein Kontextmenü mit häufig Befehle angezeigt. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.

Sie können die [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) verwenden, um Zugriffstastenbefehle mit Code zu verknüpfen. Eine Liste der vordefinierten Zugriffstasten, finden Sie unter [Zugriffstasten](../windows/predefined-accelerator-keys.md).

> [!NOTE]
> Windows lässt keine Ihnen die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.

## <a name="accelerator-properties"></a>Eigenschaften für Zugriffstasten

Sie können die Eigenschaften für Zugriffstasten festlegen, der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können auch die **Zugriffstasten-Editor** um die tastenkombinationseigenschaften in der tastenkombinationstabelle zu ändern. Änderungen, die mit der **Eigenschaften** Fenster oder der **Zugriffstasten-Editor** führen zum gleichen Ergebnis, Änderungen werden sofort in der tastenkombinationstabelle dargestellt.

Die **ID** -Eigenschaft verweist auf die einzelnen Einträge im Programmcode Accelerator. Dieser Eintrag ist der Befehlswert, den das Programm empfängt, wenn ein Benutzer die Zugriffstaste oder Tastenkombination drückt. Um einer Zugriffstaste identisch mit der ein Menüelement zu machen, stellen die **ID** identisch sind, so lange Sie die **ID** Tabelle der Zugriffstaste ist identisch mit der **ID** für die Menüressource.

Jede Zugriffstaste **ID** verfügt über drei Eigenschaften: **Modifizierer**, **Schlüssel**, und **Typ**

Die **Modifizierer** Eigenschaftensätze Steuerelement Tastenkombinationen für die Zugriffstaste.

> [!NOTE]
> In der **Eigenschaften** Fenster die **Modifizierer** Eigenschaft wird als drei Separate **booleschen** Eigenschaften, die alle davon unabhängig gesteuert werden können: **ALT**, **STRG**, und **UMSCHALT**.

Die folgende sind zulässige Einträge für die **Modifizierer** Eigenschaft in der tastenkombinationstabelle:

   |Wert|Beschreibung|
   |-----------|-----------------|
   |**Keine**|Benutzer drückt nur die **Schlüssel** Wert.<br/><br/>Dieser Wert ist am effizientesten mit den ASCII/ANSI-Werten 001 bis 026, was interpretiert wird als ^ A bis ^ Z (**STRG + A** über **STRG + Z**).|
   |**ALT**|Der Benutzer muss drücken **Alt** vor der **Schlüssel** Wert.|
   |**STRG**|Der Benutzer muss drücken **STRG** vor der **Schlüssel** Wert, mit dem ASCII-Typ ist ungültig.|
   |**UMSCHALTTASTE**|Der Benutzer muss drücken **UMSCHALT** vor der **Schlüssel** Wert.|
   |**Strg + Alt +**|Der Benutzer muss drücken **STRG** und **Alt** vor der **Schlüssel** Wert, mit dem ASCII-Typ ist ungültig.|
   |**STRG + UMSCHALT**|Der Benutzer muss drücken **STRG** und **UMSCHALT** vor der **Schlüssel** Wert, mit dem ASCII-Typ ist ungültig.|
   |**ALT + UMSCHALT**|Der Benutzer muss drücken **Alt** und **UMSCHALT** vor der **Schlüssel** Wert, mit dem ASCII-Typ ist ungültig.|
   |**Strg + Alt + Umschalt**|Der Benutzer muss drücken **STRG**, **Alt**, und **UMSCHALT** vor der **Schlüssel** Wert, mit dem ASCII-Typ ist ungültig.|

Die **Schlüssel** Eigenschaft legt fest, den tatsächlichen Schlüssel als Zugriffstaste verwenden.

Die folgende sind zulässige Einträge für die **Schlüssel** Eigenschaft in der tastenkombinationstabelle:

   |Wert|Beschreibung|
   |-----------|-----------------|
   |Eine ganze Zahl zwischen 0 und 255 im Dezimalformat.|Der Wert bestimmt, ob der Wert als ASCII oder ANSI, wie folgt behandelt wird:<br/><br/>   -Einstellige Zahlen werden immer als der entsprechende Schlüssel und nicht als ASCII oder ANSI-Werte interpretiert.<br/>   -Werte von 1 bis 26, wenn Nullen vorangestellt werden als interpretiert ^ A bis ^ Z, steht für den ASCII-Wert, der den Buchstaben des Alphabets, wenn Sie mit gedrückt der **STRG** -Taste gedrückt gehalten.<br/>   -Werte von 27-32 werden immer als drei Ziffern bestehenden Dezimalwerte 027 bis 032 interpretiert.<br/>   -Werte von 033 bis 255, 0 vorangestellt oder nicht als ANSI-Werte interpretiert werden.|
   |Ein einzelnes Zeichen der Tastatur.|Großbuchstaben von A - Z oder die Ziffern 0 – 9 können entweder ASCII- oder den virtuellen Schlüsselwerte. Alle anderen Zeichen ist ASCII nur an.|
   |Ein einzelnes Zeichen der Tastatur im Bereich von A - Z (nur Großbuchstaben), ein Caretzeichen (^) vorangestellt sind, z. B. ^ C.|Diese Option gibt den ASCII-Wert des Schlüssels aus, wenn es gedrückt wird, mit der **STRG** -Taste gedrückt gehalten.|
   |Alle gültigen virtuellen Tastenbezeichner.|Die Dropdownliste **Schlüssel** in der tastenkombinationstabelle enthält eine Liste der standardmäßigen virtuellen Schlüsselbezeichner.|

> [!NOTE]
> Bei der Eingabe von ASCII-Wert, der **Modifizierer** -Optionen beschränkt sind. Ist der einzige Steuerelement verfügbare Schlüssel für die Verwendung der **Alt** Schlüssel.

> [!TIP]
> Eine Verknüpfung mit eine Zugriffstaste zu definieren, mit der rechten Maustaste einen Eintrag oder mehrere Einträge in der Zugriffstastentabelle ist, wählen Sie dann **Nächste Taste** und beliebige der Tasten bzw. Tastenkombinationen auf der Tastatur drücken.
>
> Dies **Nächste Taste** Befehl steht auch auf die **bearbeiten** Menü.

Die **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der Zugriffstaste verknüpft **ID** wird als ein Schlüssel ASCII/ANSI-Wert oder eine Kombination der Schlüssel für ein virtuelles (VIRTKEY) interpretiert.

- Wenn die **Typ** Eigenschaft **ASCII**, **Modifizierer** Eigenschaft ist möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste, die die verwendet**STRG** Schlüssel, den Schlüssel mit abgrenzen, indem Sie gemäß einem `^`.

- Wenn die **Typ** Eigenschaft **VIRTKEY**, eine beliebige Kombination von **Modifizierer** und **Schlüssel** Werte gilt.

> [!NOTE]
> Wenn Sie verwenden möchten, geben einen Wert in der Zugriffstastentabelle-Wert behandelt, als ASCII/ANSI, wählen Sie die **Typ** für den Eintrag in der Tabelle und wählen Sie **ASCII** aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl die **bearbeiten** Menü an der **Schlüssel**, müssen Sie ändern die **Typ** Eigenschaft aus **VIRTKEY** zu **ASCII** *vor* eingeben der **Schlüssel** Code.

## <a name="accelerator-tables"></a>Zugriffstastentabellen

Sie können eine Zugriffstastentabelle in eine C++-Projekt bearbeiten, direkt mit der direkten Bearbeitung in der **Zugriffstasten-Editor**.

Die folgenden Verfahren beziehen sich auf die Verwendung von standard-Eigenschaftenseiten können jedoch die direkte Bearbeitung und der Seitenmethode für das gleiche Ergebnis. Änderungen mithilfe von Eigenschaftenseiten oder mithilfe der direkten Bearbeitung werden sofort in der tastenkombinationstabelle dargestellt.

### <a name="to-edit-in-an-accelerator-table"></a>So führen Sie die Bearbeitung in einer Zugriffstastentabelle durch

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources).

1. Wählen Sie einen Eintrag in der Tabelle, und wählen Sie auf die um direkte Bearbeitung zu aktivieren.

1. Wählen Sie aus dem Dropdown-Kombinationsfeld, oder geben Sie Änderungen vornehmen:

   - Für **ID**, wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für **Modifizierer**, wählen Sie aus der Liste.

   - Für **Schlüssel**, wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für **Typ**Option **ASCII** oder **VIRTKEY** aus der Liste.

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>So suchen Sie einen Eintrag in einer geöffneten Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources).

1. Wählen Sie eine Spaltenüberschrift, um den Inhalt der Spalte alphabetisch zu sortieren. Wählen Sie z. B. **ID** , alle IDs, die in der Zugriffstastentabelle in alphabetischer Reihenfolge anzuzeigen.

   Sie können die Liste dann durchsuchen und den gewünschten Eintrag finden.

### <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources).

1. Mit der rechten Maustaste in die Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste**, oder wählen Sie den Eintrag leere Zeile am unteren Rand der Tabelle.

1. Wählen Sie eine **ID** aus der Dropdown-Liste in der **ID** Feld, oder geben Sie einen neuen *ID* in die **ID** Feld.

1. Typ der *Schlüssel* Sie verwenden möchten, verwenden Sie als Zugriffstaste, oder mit der rechten Maustaste, und wählen **Nächste Taste** eine Tastenkombination festlegen oder wechseln Sie zum Menü **bearbeiten**  >  **Nächste Taste**.

1. Ändern der **Modifizierer** und **Typ**, falls erforderlich, und drücken Sie die **EINGABETASTE**.

> [!NOTE]
> Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Sie können mehrere Tastenkombinationen ohne weitere Auswirkungen, z. B. dieselbe ID zugewiesen haben **STRG**+**P** und **F8** "id_print" zugewiesen werden. Allerdings müssen Sie eine Tastenkombination zugewiesen mit ID nicht, z. B. funktioniert mehr als einem **STRG**+**Z** sowohl "ID_SPELL_CHECK" und "Dies zugewiesen.

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>So löschen Sie einen Eintrag aus einer Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources).

1. Wählen Sie den Eintrag zu löschen, oder halten Sie die **STRG** oder **UMSCHALT** gedrückt, während Sie auswählen, um mehrere Einträge auszuwählen.

1. Mit der rechten Maustaste, und wählen Sie **löschen**, oder wechseln Sie zum Menü **bearbeiten** > **löschen**.

> [!TIP]
> Drücken Sie die **löschen** Schlüssel zu löschen.

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>So verschieben oder kopieren Sie einen Eintrag in einer Zugriffstastentabelle in eine andere Ressourcenskriptdatei

1. Öffnen Sie in beiden Ressourcenskriptdateien die Zugriffstastentabellen, und wählen Sie den Eintrag, die, den Sie verschieben möchten.

1. Von der **bearbeiten** Menü wählen **Kopie** oder **Ausschneiden**.

1. Wählen Sie einen Eintrag in der Ziel-Ressourcenskriptdatei und von der **bearbeiten** Menü wählen **einfügen**.

> [!NOTE]
> Zum Kopieren und Einfügen können Sie auch Tastenkombinationen verwenden.

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Zum Ändern der Eigenschaften mehrerer Zugriffstasten

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](/windows/how-to-create-a-resource-script-file#create-resources).

1. Wählen Sie die Zugriffstasten, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie jede auswählen.

1. Wechseln Sie zu der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) , und geben Sie die Werte aller ausgewählten Zugriffstasten freigeben.

> [!NOTE]
> Jeder Modifiziererwert angezeigt wird, als eine boolesche Eigenschaft in der **Eigenschaften** Fenster. Wenn Sie ändern eine [Modifizierer](../windows/accelerator-modifier-property.md) Wert in der **Eigenschaften** Fenster die Zugriffstastentabelle behandelt den new-Modifizierer als eine Erweiterung für alle Modifizierer, die bereits vorhanden waren. Aus diesem Grund setzen Sie alle Modifiziererwerte, Sie müssen alle Angaben, um sicherzustellen, dass alle Zugriffstasten dasselbe festlegen **Modifizierer** Einstellungen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Zugriffstasten](../windows/predefined-accelerator-keys.md)<br/>