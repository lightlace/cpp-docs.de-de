---
title: Markieren von Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
ms.author: Michael.Blome
ms.topic: tutorial
ms.service: cpp
author: mikeblome
ms.openlocfilehash: 008c99ae4b2cba5ff8f8b9ab069bb1b8085b7524
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293636"
---
# <a name="selecting-controls"></a>Markieren von Steuerelementen

Auswählen von Steuerelementen auf Größe, ausrichten, verschieben, kopieren, oder löschen, und schließen Sie dann den gewünschten Vorgang. In den meisten Fällen müssen Sie zu verwenden, die Tools zur größenanpassung und die Ausrichtung auf mehrere Steuerelement auswählen, die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Wenn ein Steuerelement ausgewählt ist, einen schattierten Rahmen mit Solid (aktiv hat) oder leere (deaktivierte) "Ziehpunkten" kleine, die Quadrate in den Auswahlrahmen angezeigt werden. Wenn mehrere Steuerelemente ausgewählt sind, wird das dominante Steuerelement hat gefüllte Ziehpunkte, und alle anderen ausgewählten Steuerelemente haben leere Ziehpunkte.

Beim Ändern der Größe oder Ausrichtung mehrerer Steuerelemente, die **Dialogfeld** Editor verwendet, das "dominante Steuerelement" um zu bestimmen, wie die anderen Steuerelemente angepasst oder ausgerichtet sind. Standardmäßig ist das dominante Steuerelement das erste Steuerelement ausgewählt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-select-multiple-controls"></a>Zum Auswählen mehrerer Steuerelemente

1. In der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), wählen die **Zeiger** Tool.

1. Ziehen Sie den Mauszeiger, um ein Auswahlfeld um Steuerelemente zu zeichnen, die Sie in einem Dialogfeld auswählen möchten.

   Wenn Sie die Maustaste loslassen, alle Steuerelemente innerhalb und sich überschneiden, werden das Auswahlfeld ausgewählt.

   \- oder –

   Halten Sie die **UMSCHALT** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

   \- oder –

   Halten Sie die **STRG** gedrückt, und wählen Sie die Steuerelemente, die Sie in der Auswahl einschließen möchten.

## <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Ein Steuerelement aus einer Gruppe von ausgewählten Steuerelemente zu entfernen oder Hinzufügen des Steuerelements auf eine Gruppe von ausgewählten Steuerelemente

1. Mit der eine Gruppe von Steuerelementen, die ausgewählt werden soll, halten Sie die **UMSCHALT** gedrückt, und wählen Sie das Steuerelement, das Sie verwenden möchten, um die vorhandene Auswahl hinzufügen oder daraus entfernen.

   > [!NOTE]
   > Gedrückt der **STRG** -Taste und der Auswahl eines Steuerelements in eine Auswahl treffen, die in die Auswahl des bestimmenden Steuerelements zu steuern.

## <a name="to-specify-the-dominant-control"></a>Zum Angeben des bestimmenden Steuerelements

1. Halten Sie die **STRG** gedrückt, und klicken Sie auf das Steuerelement, das Sie nutzen, um die Größe oder Position von anderen Steuerelementen beeinflussen möchten *erste*.

> [!NOTE]
> Die Ziehpunkte des bestimmenden Steuerelements sind solid, während die Ziehpunkte der untergeordneten Steuerelemente leer sind. Alle weiteren Ändern der Größe oder Ausrichtung basiert auf das dominante Steuerelement.

## <a name="to-change-the-dominant-control"></a>Ändern des bestimmenden Steuerelements

1. Löschen Sie die aktuelle Auswahl, indem Sie die außerhalb aller derzeit ausgewählten Steuerelemente auf.

1. Wiederholen Sie die vorherigen Schritte, und wählen ein anderes Steuerelement zuerst aus.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)