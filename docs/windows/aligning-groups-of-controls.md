---
title: Ausrichten von Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
ms.assetid: a4f49a73-4a17-44b3-8568-aa35f646b5cf
ms.openlocfilehash: abfae0f0146fa736a6427eb1180805717ce8a78e
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484980"
---
# <a name="align-controls"></a>Ausrichten von Steuerelementen

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

Die folgenden Verfahren zeigen, wie zum Ausrichten von Steuerelementen:

## <a name="to-align-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

1. [Wählen Sie die Steuerelemente](../windows/selecting-multiple-controls.md) Sie ausrichten möchten. Achten Sie darauf, um das Steuerelement auszuwählen, die das dominante Steuerelement werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen von die Ausrichtung, oder Ändern der Größe Befehl sein.

   Die letzte Position in der Gruppe von Steuerelementen, hängt von der Position des bestimmenden Steuerelements ab. Weitere Informationen zum Auswählen des bestimmenden Steuerelements finden Sie unter [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md).

1. Von der **Format** Menü wählen **ausrichten**, und wählen Sie dann eines der folgenden Ausrichtungen:

   - `Lefts`: Richtet die ausgewählten Steuerelemente an die linke Seite.

   - `Centers`: Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt aus.

   - `Rights`: Richtet die ausgewählten Steuerelemente an die rechte Seite.

   - `Tops`: Richtet die ausgewählten Steuerelemente an die oberen Ränder.

   - `Middles`: Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt aus.

   - `Bottoms`: Richtet die ausgewählten Steuerelemente an die unteren Rand.

## <a name="to-even-the-spacing-between-controls"></a>Sogar den Abstand zwischen Steuerelementen

Die **Dialogfeld** -Editor können Sie an Steuerelemente der Platz gleichmäßig auf die äußersten Steuerelemente ausgewählt.

1. Wählen Sie die Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **gleichmäßig**, und wählen Sie dann eine der folgenden Ausrichtungsbefehle:

   - `Across`: Steuerelemente gleichmäßig zwischen dem äußeren linken und dem äußersten rechten ausgewählten Steuerelement Speicherplatz.

   - `Down`: Speicherplatz Steuerelemente gleichmäßig zwischen dem obersten und untersten Steuerelements ausgewählt.

## <a name="to-center-controls-in-a-dialog-box"></a>Zentrieren von Steuerelementen in einem Dialogfeld

1. Wählen Sie das Steuerelement oder Steuerelemente, die Sie neu anordnen möchten.

1. Von der **Format** Menü wählen **Center im Dialogfeld**, und wählen Sie dann eine der folgenden Aktionen:

   - `Vertical`: die Steuerelemente in das Dialogfeld vertikal zentrieren.

   - `Horizontal`: Steuerelemente im Dialogfeld horizontal zentriert.

## <a name="to-arrange-push-buttons-along-the-right-or-bottom-of-a-dialog-box"></a>Anordnen von Schaltflächen am rechten oder unteren Rand eines Dialogfelds

1. Wählen Sie eine oder mehrere Schaltflächen an.

1. Von der **Format** Menü wählen **Schaltflächen anordnen**, und wählen Sie dann eine der folgenden Aktionen:

   - `Right`: Richtet die Schaltflächen am rechten Rand des Dialogfelds.

   - `Bottom`: Richtet die Schaltflächen am unteren Rand des Dialogfelds.

       Wenn Sie ein Steuerelement als eine Schaltfläche auswählen, wird nicht seine Position beeinflusst.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)