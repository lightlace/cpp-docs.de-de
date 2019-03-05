---
title: Manuelles Hinzufügen von Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: c70539b49fcf2aa87f0bee375a87b38277b6ed42
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270760"
---
# <a name="adding-controls-by-hand"></a>Manuelles Hinzufügen von Steuerelementen

Sie können entweder [Hinzufügen von Steuerelementen zu einem Dialogfeld mit den Dialog-Editor](../mfc/using-the-dialog-editor-to-add-controls.md) oder hinzufügen, selbst mit Code.

Um ein Steuerelementobjekt selbst zu erstellen, werden Sie in der Regel die C++-Control-Objekt in einem C++-Dialog oder Rahmenfensterobjekt einbetten. Wie bei vielen anderen Objekten im Framework erfordern Steuerelemente Erstellung in zwei Schritten. Sie sollten des Steuerelements aufrufen **erstellen** Memberfunktion, die im Rahmen der Erstellung des übergeordnete Dialogfeld Feld oder den Frame-Fensters. Für Dialogfelder, dies erfolgt normalerweise [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), und für die Frame-Fensters, in [OnCreate](../mfc/reference/cwnd-class.md#oncreate).

Das folgende Beispiel zeigt, wie Sie deklarieren, können ein `CEdit` -Objekt in der Deklaration einer Dialogfeldklasse abgeleiteten, und rufen Sie dann die `Create` -Memberfunktion im `OnInitDialog`. Da die `CEdit` Objekt als eingebettetes Objekt deklariert ist, es wird automatisch erstellt, wenn das Dialogfeldobjekt wird erstellt, aber es immer noch mit eigenem initialisiert werden muss `Create` Member-Funktion.

[!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]

Die folgenden `OnInitDialog` Funktion richtet ein Rechteck, ruft dann `Create` erstellen das Steuerelement zum Bearbeiten von Windows, und fügen Sie ihn an den nicht initialisierten `CEdit` Objekt.

[!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]

Nach der Edit-Objekt erstellt haben, können Sie auch den Eingabefokus auf das Steuerelement festlegen, durch Aufrufen der `SetFocus` Member-Funktion. Zum Schluss Sie 0 aus zurückgeben `OnInitDialog` an, dass der Fokus festgelegt. Wenn Sie einen Wert ungleich NULL zurückgegeben wird, setzt die Dialogfeld-Manager den Fokus auf das erste Steuerelement-Element in der Liste der Dialogfeld-Element. In den meisten Fällen sollten Sie die Steuerelemente in den Dialogfeldern der Dialog-Editor Hinzufügen.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)<br/>
[CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)
