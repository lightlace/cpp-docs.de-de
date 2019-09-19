---
title: 'Beispiel: Anzeigen eines Dialog Felds über einen Menübefehl'
ms.date: 09/07/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 12c919c1c79a3e40a1322f3f73398b90af2fad5f
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095926"
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Beispiel: Anzeigen eines Dialog Felds über einen Menübefehl

Dieses Thema enthält Verfahren für Folgendes:

- Zeigt ein modales Dialogfeld mithilfe eines Menübefehls an.

- Zeigt ein Dialogfeld ohne Modus über einen Menübefehl an.

Beide Beispiel Prozeduren gelten für MFC-Anwendungen und funktionieren in einer Anwendung, die Sie mit dem [MFC-Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md)erstellen.

Die Prozeduren verwenden die folgenden Namen und Werte:

|Element|Name oder Wert|
|----------|-------------------|
|Application|Display Dialog|
|Menübefehl|Befehl "Test" im Menü "Ansicht" Befehls-ID = ID_VIEW_TEST|
|Dialogfeld|Dialogfeld "Test"; Class = CTestDialog; Header Datei = testDialog. h; Variable = testdlg, ptestdlg|
|Befehls Handler|OnViewTest|

### <a name="to-display-a-modal-dialog-box"></a>So zeigen Sie ein modales Dialogfeld an

1. Erstellen Sie den Menübefehl. Weitere Informationen finden Sie unter [Erstellen von Menüs oder Menü Elementen](../windows/creating-a-menu.md).

1. Dialogfeld erstellen; siehe [Starten des Dialog-Editors](../windows/creating-a-new-dialog-box.md).

1. Fügen Sie eine Klasse für das Dialogfeld hinzu. Weitere Informationen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) .

1. Wählen Sie in **Klassenansicht**die Document-Klasse (CDisplayDialogDoc) aus. Klicken Sie im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse** . Doppelklicken Sie auf die ID des Menübefehls (ID_VIEW_TEST). Klicken Sie anschließend auf den Pfeil nach unten, und wählen Sie  **\<> OnViewTest hinzufügen**aus.

   Wenn Sie den Menübefehl dem Main Frame einer MDI-Anwendung hinzugefügt haben, wählen Sie stattdessen die Anwendungsklasse (CDisplayDialogApp) aus.

1. Fügen Sie die folgende include-Anweisung zu CDisplayDialogDoc. cpp (oder CDisplayDialogApp. cpp) nach den vorhandenen include-Anweisungen hinzu:

   ```cpp
   #include "TestDialog.h"
   ```

1. Fügen Sie den folgenden Code `OnViewTest` hinzu, um die-Funktion zu implementieren:

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal(); 
   ```

### <a name="to-display-a-modeless-dialog-box"></a>So zeigen Sie ein nicht modalem Dialogfeld an

1. Führen Sie die ersten vier Schritte aus, um ein modales Dialogfeld anzuzeigen, außer wählen Sie die Ansichts Klasse (cdisplaydialogview) in Schritt 4 aus.

1. Bearbeiten Sie die Datei "displaydialogview. h":

   - Deklarieren Sie die Dialogfeld Klasse vor der ersten Klassen Deklaration:

   ```cpp
   class CTestDialog;
   ```

   - Einen Zeiger auf das Dialogfeld nach dem öffentlichen Abschnitt Attribute deklarieren:

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. Bearbeiten Sie displaydialogview. cpp:

   - Fügen Sie die folgende include-Anweisung nach den vorhandenen include-Anweisungen hinzu:

   ```cpp
   #include "TestDialog.h"
   ```

   - Fügen Sie dem Konstruktor den folgenden Code hinzu:

   ```cpp
   m_pTestDlg = NULL;
   ```

   - Fügen Sie dem Dekonstruktor den folgenden Code hinzu:

   ```cpp
   delete m_pTestDlg;
   ```

   - Fügen Sie den folgenden Code `OnViewTest` hinzu, um die-Funktion zu implementieren:

   ```cpp
   if (NULL == m_pTestDlg)
   {
      m_pTestDlg = new CTestDialog(this);
      m_pTestDlg->Create(CTestDialog::IDD, this);
   }
   m_pTestDlg->ShowWindow(SW_SHOW);
   ```

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)
