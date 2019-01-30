---
title: Festlegen von Eigenschaften für Zugriffstasten (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
- VIRTKEY
- Key property
- ID property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
ms.openlocfilehash: e1fac31635b7ccc09f9c184cf734fa4f7717cb97
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232135"
---
# <a name="setting-accelerator-properties"></a>Festlegen von Zugriffstasteneigenschaften

Sie können die Eigenschaften für Zugriffstasten festlegen, der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zu einem beliebigen Zeitpunkt. Sie können auch die [Zugriffstasten-Editor](../windows/accelerator-editor.md) um die tastenkombinationseigenschaften in der tastenkombinationstabelle zu ändern. Änderungen, die mit der **Eigenschaften** Fenster oder der **Accelerator** Editor aufweisen, das gleiche Ergebnis: Änderungen werden sofort in der tastenkombinationstabelle dargestellt.

## <a name="id-property"></a>ID-Eigenschaft

Die **ID** -Eigenschaft verweist auf die einzelnen Einträge im Programmcode Accelerator. Dieser Eintrag ist der Befehlswert, den das Programm erhalten sollen, wenn ein Benutzer die Zugriffstaste oder Tastenkombination drückt. Um einer Zugriffstaste identisch mit der ein Menüelement zu machen, müssen Sie deren IDs identisch (sofern die ID der Tabelle mit Zugriffstasten wird die die ID für die Menüressource identisch ist).

Es gibt drei Eigenschaften für jede ID der Zugriffstaste: die **Modifizierer** -Eigenschaft, die **Schlüssel** -Eigenschaft, und die **Typ** Eigenschaft.

## <a name="modifier-property"></a>Modifier-Eigenschaft

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

## <a name="key-property"></a>Key-Eigenschaft

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

## <a name="type-property"></a>Type-Eigenschaft

Die **Typ** Eigenschaft bestimmt, ob die Tastenkombination mit der ID der Zugriffstaste verknüpft ist als ein ASCII/ANSI-Schlüssel-Wert oder eine Kombination der Schlüssel für ein virtuelles (VIRTKEY) interpretiert wird.

- Wenn der **Typ** -Eigenschaft ist ASCII, die **Modifizierer** Eigenschaft ist möglicherweise nur `None` oder `Alt`, oder es kann eine Zugriffstaste, die verwendet die **STRG** Schlüssel () angegeben, die den Schlüssel mit abgrenzen, indem Sie eine `^`).

- Wenn die **Typ** -Eigenschaft ist VIRTKEY, eine beliebige Kombination von `Modifier` und `Key` Werte gilt.

> [!NOTE]
> Wenn Sie verwenden möchten, geben einen Wert in die Zugriffstastentabelle, und den Wert als ASCII/ANSI, klicken Sie behandelt werden die **Typ** für den Eintrag in der Tabelle und wählen Sie ASCII aus der Dropdownliste aus. Jedoch bei Verwendung der **Nächste Taste** Befehl (**bearbeiten** im Menü) an die `Key`, müssen Sie ändern die **Typ** Eigenschaft von VIRTKEY ASCII *vor* eingeben der `Key` Code.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Änderungen innerhalb einer Zugriffstastentabelle](../windows/editing-in-an-accelerator-table.md)<br/>
[Vordefinierte Zugriffstasten](../windows/predefined-accelerator-keys.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
