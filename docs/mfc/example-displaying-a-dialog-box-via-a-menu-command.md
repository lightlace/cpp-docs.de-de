---
title: 'Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2869e936115317ff34183b55ba16fe8e9cdc4d2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378188"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl

Dieses Thema enthält Verfahren zum:

- Über einen Menübefehl ein modales Dialogfeld wird angezeigt.

- Über einen Menübefehl ein nicht modales Dialogfeld wird angezeigt.

Beide Beispielprozeduren sind für MFC-Anwendungen und funktioniert in einer Anwendung, die Sie erstellen, mit der [MFS-Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md).

Die Verfahren verwenden Sie die folgenden Namen und Werte:

|Element|Namen oder Wert|
|----------|-------------------|
|Application|DisplayDialog|
|Kontextmenübefehl von ""|Testbefehl im Menü "Ansicht"; Befehls-ID = ID_VIEW_TEST|
|Dialogfeld|Dialogfeld "Test"; Klasse = CTestDialog; Headerdatei = TestDialog.h; Variable = Testdlg, Ptestdlg|
|Befehlshandler|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>Um ein modales Dialogfeld anzuzeigen.

1. Erstellen Sie den Menübefehl; finden Sie unter [Menüs erstellen oder Menüelemente](../windows/creating-a-menu.md).

1. Erstellen Sie im Dialogfeld an; finden Sie unter [starten den Dialog-Editor](../windows/creating-a-new-dialog-box.md).

1. Fügen Sie eine Klasse für das Dialogfeld. Finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) für Weitere Informationen.

1. In **Klassenansicht**, wählen Sie die Dokumentklasse (CDisplayDialogDoc). Klicken Sie im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse** . Doppelklicken Sie auf die ID des Menübefehls (ID_VIEW_TEST) im linken Bereich die **Eigenschaften** Fenster, und wählen **Befehl**. Klicken Sie im rechten Bereich auf den Pfeil nach unten, und wählen Sie  **\<hinzufügen > OnViewTest**.

     Wenn Sie den Menübefehl mit dem Großrechner einer MDI-Anwendung hinzugefügt haben, wählen Sie stattdessen die Anwendungsklasse (CDisplayDialogApp).

1. Fügen Sie die folgenden include-Anweisung, um CDisplayDialogDoc.cpp (oder CDisplayDialogApp.cpp) nach den vorhandenen Anweisungen einschließen:

     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

1. Fügen Sie den folgenden Code `OnViewTest` der Funktion implementiert wird:

     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]

### <a name="to-display-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld angezeigt.

1. Führen Sie die ersten vier Schritte, um ein modales Dialogfeld, mit der Ausnahme die Ansichtsklasse (CDisplayDialogView) Wählen Sie in Schritt 4 angezeigt.

1. Bearbeiten Sie DisplayDialogView.h:

   - Die Dialogfeldklasse, die vor der Deklaration der ersten Klasse zu deklarieren:

         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]

   - Einen Zeiger auf das Dialogfeld nach dem öffentlichen Abschnitt der Attribute zu deklarieren:

         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]

1. Bearbeiten Sie DisplayDialogView.cpp:

   - Fügen Sie die folgende Anweisung einschließen, nach den vorhandenen include-Anweisungen hinzu:

         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]

   - Fügen Sie dem Konstruktor den folgenden Code hinzu:

         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]

   - Fügen Sie den folgenden Code, der Destruktor:

         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]

   - Fügen Sie den folgenden Code `OnViewTest` der Funktion implementiert wird:

         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]

Darüber hinaus finden Sie im folgenden Knowledge Base-Artikel:

- Q251059: So wird's gemacht: Geben Sie Ihre eigenen Fensterklassenname für MFC-Dialogfeld

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)

