---
title: Anpassen von Steuerelementen
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
ms.openlocfilehash: a6381dcf1aeb9f73ac3b656229d9332df2a6a519
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742712"
---
# <a name="sizing-controls"></a>Anpassen von Steuerelementen

Verwenden Sie die Ziehpunkte, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert es Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Es sind aktive Ziehpunkte gefüllt. Wenn ein Ziehpunkt leerer ist, kann nicht das Steuerelement entlang dieser Achse Größe geändert werden.

Sie können auch die Größe eines Steuerelements ändern, durch das das Steuerelement an Führungslinien oder Rand andocken, oder durch das Verschieben einer Kontrolle und Anleitung von einem anderen angedockt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-size-an-individual-control"></a>Ein einzelnes Steuerelement seine Größe festlegen

1. Wählen Sie das Steuerelement.

1. Ziehen Sie die Ziehpunkte, um die Größe des Steuerelements zu ändern:

   - Ziehpunkte an den oberen und den Seiten die horizontale oder vertikale Größe geändert.

   - Ziehpunkte an den Ecken ändern Sie horizontale und vertikale Größe.

   > [!TIP]
   > Sie können die Steuerelement ein Dialog-Einheit (DLU) zu einem Zeitpunkt ändern, halten die **UMSCHALT** Schlüssel- und unter Verwendung der **Pfeil nach rechts** und **nach-unten-** Schlüssel.

## <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Automatisch die Größe ein Steuerelement für den Text angepasst

Wählen Sie **Größe an Inhalt anpassen** aus der **Format** Menü.

\- oder –

Klicken Sie auf das Steuerelement, und wählen Sie **Größe an Inhalt anpassen** aus dem Kontextmenü.

## <a name="to-make-controls-the-same-width-height-or-size"></a>Um machen steuert die gleiche Breite, Höhe oder Größe

Sie können eine Gruppe von Steuerelementen basierend auf der Größe des bestimmenden Steuerelements ändern.

1. [Wählen Sie die Steuerelemente](../windows/selecting-multiple-controls.md) Sie anpassen möchten.

   Das Steuerelement zuerst in der Reihe ausgewählt ist, das dominante Steuerelement. Die endgültige Größe der Steuerelemente in der Gruppe, hängt von der Größe des bestimmenden Steuerelements ab. Weitere Informationen zum Auswählen des bestimmenden Steuerelements finden Sie unter [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md).

1. Von der **Format** Menü wählen **Größe angleichen**, wählen Sie dann eine der folgenden Befehle aus:

   - **Both**

   - **Height**

   - **Width**

## <a name="to-set-the-size-of-the-combo-box-and-its-drop-down-list"></a>Die Größe des Kombinationsfeld Feld und der Dropdown-Liste festgelegt

Sie können ein Kombinationsfeld Größe, wenn Sie sie zum Dialogfeld hinzufügen. Sie können auch die Größe des im Dropdown-Listenfeld angeben. Weitere Informationen finden Sie unter [Werte hinzufügen, um ein Kombinationsfeld-Steuerelement](../windows/adding-values-to-a-combo-box-control.md).

### <a name="to-size-a-combo-box"></a>Die Größe eines Kombinationsfelds

1. Wählen Sie das Kombinationsfeld-Steuerelement in einem Dialogfeld an.

   Anfangs sind nur die Rechte und linke Ziehpunkt aktiv.

1. Verwenden Sie die Ziehpunkte, um die Breite des Kombinationsfelds festzulegen.

Sie können auch die vertikale Größe des der Dropdownteil des Kombinationsfelds festlegen.

### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Zum Festlegen von der Größe des Kombinationsfeld-Dropdown-Liste

1. Wählen Sie die Dropdown-Pfeil-Schaltfläche rechts neben dem Kombinationsfeld aus.

   ![Pfeil in einem Kombinationsfeld in einem MFC-Projekt](../mfc/media/vccomboboxarrow.gif "VcComboBoxArrow")

   Die Gliederung des Steuerelements ändert die Größe des Kombinationsfelds mit den erweiterten Dropdown-Listenfeld-Bereich angezeigt.

1. Verwenden Sie den unteren Ziehpunkt, um die Anfangsgröße des Bereichs, Dropdown-Listenfeld ändern.

   ![Kombinationsfeld&#45;Box-Sizing in einem MFC-Projekt](../mfc/media/vccomboboxsizing.gif "VcComboBoxSizing")

1. Wählen Sie den Dropdown-Pfeil erneut aus, um der Teil der Dropdown-Listenfeld des Kombinationsfelds geschlossen.

## <a name="to-set-the-width-of-a-horizontal-scroll-bar-and-make-it-appear"></a>Legen Sie die Breite einer horizontalen Schiebeleiste, und stellen es so aussieht

Wenn Sie ein Listenfeld mit einer horizontalen Schiebeleiste eines Dialogfelds mithilfe von MFC-Klassen hinzufügen, wird nicht die Bildlaufleiste automatisch in Ihrer Anwendung angezeigt.

Legen Sie eine maximale Breite für das breiteste Element durch Aufrufen von [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) in Ihrem Code.

   Ohne diesen Wert wird nicht die Bildlaufleiste angezeigt, auch wenn die Elemente im Listenfeld breiter als das Feld sind.
> [!NOTE]
> Die horizontale Bildlaufleiste erfordert MFC.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
