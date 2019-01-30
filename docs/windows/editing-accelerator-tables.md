---
title: Bearbeiten von Zugriffstastentabellen (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
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
ms.assetid: 56e24efb-d06b-4ed9-8915-1f99f725e247
ms.openlocfilehash: dfa0c26132378bcbe8a7f5203351134d91746aa7
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232174"
---
# <a name="editing-accelerator-tables-c"></a>Bearbeiten von Zugriffstastentabellen (C++)

Sie können eine Zugriffstastentabelle in eine C++-Projekt bearbeiten, direkt mit der direkten Bearbeitung in der **Accelerator** Editor.

Die folgenden Verfahren beziehen sich auf die Verwendung von standard-Eigenschaftenseiten können jedoch die direkte Bearbeitung und der Seitenmethode für das gleiche Ergebnis. Änderungen mithilfe von Eigenschaftenseiten oder mithilfe der direkten Bearbeitung werden sofort in der tastenkombinationstabelle dargestellt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

## <a name="to-edit-in-an-accelerator-table"></a>So führen Sie die Bearbeitung in einer Zugriffstastentabelle durch

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie einen Eintrag in der Tabelle, und wählen Sie auf die um direkte Bearbeitung zu aktivieren.

1. Treffen Sie eine Auswahl im Dropdown-Kombinationsfeld, oder geben Sie diese direkt ein, um Änderungen vornehmen.

   - Für [ID](id-property.md), wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für [Modifizierer](../windows/accelerator-modifier-property.md), wählen Sie aus der Liste.

   - Für [Schlüssel](../windows/accelerator-key-property.md), wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für [Typ](../windows/accelerator-type-property.md)Option **ASCII** oder **VIRTKEY** aus der Liste.

## <a name="to-find-an-entry-in-an-open-accelerator-table"></a>So suchen Sie einen Eintrag in einer geöffneten Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie eine Spaltenüberschrift, um den Inhalt der Spalte alphabetisch zu sortieren. Wählen Sie z. B. **ID** , alle IDs, die in der Zugriffstastentabelle in alphabetischer Reihenfolge anzuzeigen.

Sie können die Liste dann durchsuchen und den gewünschten Eintrag finden.

## <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Mit der rechten Maustaste in die Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste** über das Kontextmenü, oder wählen Sie den Eintrag leere Zeile am unteren Rand der Tabelle.

1. Wählen Sie eine [ID](id-property.md) Feld aus der Dropdown-Liste in die ID, oder geben Sie eine neue ID in der **ID** Feld.

1. Typ der [Schlüssel](../windows/accelerator-key-property.md) Sie verwenden möchten, verwenden Sie als eine Zugriffstaste oder eine mit der rechten Maustaste, und wählen **Nächste Taste** aus dem Kontextmenü aus, um eine Tastenkombination festzulegen (der **Nächste Taste** Befehl ist auch verfügbar in der **bearbeiten** Menü).

1. Ändern der [Modifizierer](../windows/accelerator-modifier-property.md) und [Typ](../windows/accelerator-type-property.md), falls erforderlich.

1. Drücken Sie die **EINGABETASTE**.

   > [!NOTE]
   > Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Sie können mehrere Tastenkombinationen ohne weitere Auswirkungen, z. B. dieselbe ID zugewiesen haben **STRG** + **P** und **F8** "id_print" zugewiesen werden. Allerdings müssen Sie eine Tastenkombination zugewiesen mit ID nicht, z. B. funktioniert mehr als einem **STRG** + **Z** sowohl "ID_SPELL_CHECK" und "Dies zugewiesen.

## <a name="to-delete-an-entry-from-an-accelerator-table"></a>So löschen Sie einen Eintrag aus einer Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie den zu löschenden Eintrag aus. (Halten Sie die **STRG** oder **UMSCHALT** gedrückt, während Sie auswählen, um mehrere Einträge auszuwählen.)

1. Mit der rechten Maustaste, und wählen Sie **löschen** aus dem Kontextmenü (oder wählen Sie **löschen** aus der **bearbeiten** Menü).

\- oder –

- Drücken Sie die **löschen** Schlüssel.

## <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>So verschieben oder kopieren Sie einen Eintrag in einer Zugriffstastentabelle in eine andere Ressourcenskriptdatei

1. Öffnen Sie in beiden Ressourcenskriptdateien die Zugriffstastentabellen.

1. Markieren Sie den Eintrag, der verschoben werden soll.

1. Von der **bearbeiten** Menü wählen **Kopie** oder **Ausschneiden**.

1. Markieren Sie einen Eintrag in der Ziel-Ressourcenskriptdatei.

1. Von der **bearbeiten** Menü wählen **einfügen**.

   > [!NOTE]
   > Zum Kopieren und Einfügen können Sie auch Tastenkombinationen verwenden.

## <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Zum Ändern der Eigenschaften mehrerer Zugriffstasten

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

1. Wählen Sie die Zugriffstasten, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie jede auswählen.

1. Wechseln Sie zu der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) , und geben Sie die Werte aller ausgewählten Zugriffstasten freigeben.

   > [!NOTE]
   > Jeder Modifiziererwert angezeigt wird, als eine boolesche Eigenschaft in der **Eigenschaften** Fenster. Wenn Sie ändern eine [Modifizierer](../windows/accelerator-modifier-property.md) Wert in der **Eigenschaften** Fenster die Zugriffstastentabelle behandelt den new-Modifizierer als eine Erweiterung für alle Modifizierer, die bereits vorhanden waren. Aus diesem Grund setzen Sie alle Modifiziererwerte, Sie benötigen, legen Sie alle Angaben, um sicherzustellen, dass alle Zugriffstasten dasselbe **Modifizierer** Einstellungen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zugriffstasten-Editor](../windows/accelerator-editor.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)
