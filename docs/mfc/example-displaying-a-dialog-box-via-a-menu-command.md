---
title: 'Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], examples
- MFC dialog boxes [MFC], displaying
- modeless dialog boxes [MFC], displaying
- dialog boxes [MFC], MFC
- modal dialog boxes [MFC], displaying
- examples [MFC], dialog boxes
- menu items [MFC], examples
ms.assetid: e8692549-acd7-478f-9c5e-ba310ce8cccd
ms.openlocfilehash: 1e730125e47609f0bf87814b32962336cb752b04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173300"
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

   ```cpp
   #include "TestDialog.h"
   ```

1. Fügen Sie den folgenden Code `OnViewTest` der Funktion implementiert wird:

   ```cpp
   CTestDialog testdlg;
   testdlg.DoModal();  
   ```

### <a name="to-display-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld angezeigt.

1. Führen Sie die ersten vier Schritte, um ein modales Dialogfeld, mit der Ausnahme die Ansichtsklasse (CDisplayDialogView) Wählen Sie in Schritt 4 angezeigt.

1. Edit DisplayDialogView.h:

   - Die Dialogfeldklasse, die vor der Deklaration der ersten Klasse zu deklarieren:

   ```cpp
   class CTestDialog;
   ```

   - Einen Zeiger auf das Dialogfeld nach dem öffentlichen Abschnitt der Attribute zu deklarieren:

   ```cpp
   CTestDialog* m_pTestDlg;
   ```

1. Edit DisplayDialogView.cpp:

   - Fügen Sie die folgende Anweisung einschließen, nach den vorhandenen include-Anweisungen hinzu:

   ```cpp
   #include "TestDialog.h"
   ```

   - Fügen Sie dem Konstruktor den folgenden Code hinzu:

   ```cpp
   m_pTestDlg = NULL;
   ```

   - Fügen Sie den folgenden Code, der Destruktor:

   ```cpp
   delete m_pTestDlg;
   ```

   - Fügen Sie den folgenden Code `OnViewTest` der Funktion implementiert wird:

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
