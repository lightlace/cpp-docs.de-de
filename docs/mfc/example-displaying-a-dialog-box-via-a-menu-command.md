---
title: "Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e2715e1b64c1565d122f6eec012a8a33c2525ac9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="example-displaying-a-dialog-box-via-a-menu-command"></a>Beispiel: Anzeigen eines Dialogfelds mit einem Menübefehl
Dieses Thema enthält Verfahren zum:  
  
-   Zeigt ein modales Dialogfeld über einen Menübefehl.  
  
-   Zeigen Sie ein nicht modales Dialogfeld über einen Menübefehl ein.  
  
 Beide Beispielverfahren sind für MFC-Anwendungen und funktioniert in einer Anwendung, die Sie erstellen, mit der [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md).  
  
 Mithilfe der Verfahren, die folgenden Namen und Werte:  
  
|Element|Namen oder Wert|  
|----------|-------------------|  
|Application|DisplayDialog|  
|Menübefehl|Test-Befehle im Menü "Ansicht" Befehls-ID = ID_VIEW_TEST|  
|Dialogfeld|Dialogfeld "Test"; Klasse = CTestDialog; Headerdatei = TestDialog.h; Variable = Testdlg Ptestdlg|  
|Der Befehlshandler|OnViewTest|  
  
### <a name="to-display-a-modal-dialog-box"></a>Um ein modales Dialogfeld anzuzeigen.  
  
1.  Erstellen Sie den Menübefehl aus. finden Sie unter [Menüs erstellen oder Menüelemente](../windows/creating-a-menu.md).  
  
2.  Erstellen Sie das Dialogfeld. finden Sie unter [Starten des Dialog-Editors](../windows/creating-a-new-dialog-box.md).  
  
3.  Fügen Sie eine Klasse für das Dialogfeld. Finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) für Weitere Informationen.  
  
4.  In **Klassenansicht**, wählen Sie die Dokumentklasse (CDisplayDialogDoc). Klicken Sie im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse** . Doppelklicken Sie auf die ID des Menübefehls (ID_VIEW_TEST) im linken Bereich des der **Eigenschaften** und wählen Sie **Befehl**. Klicken Sie im rechten Bereich auf den Pfeil nach unten, und wählen Sie  **\<hinzufügen > OnViewTest**.  
  
     Wenn Sie den Menübefehl mit dem Großrechner einer MDI-Anwendung hinzugefügt haben, wählen Sie stattdessen die Anwendungsklasse (CDisplayDialogApp).  
  
5.  Fügen Sie Folgendes include-Anweisung, um CDisplayDialogDoc.cpp (oder CDisplayDialogApp.cpp) nach den vorhandenen include-Anweisungen:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
6.  Fügen Sie folgenden Code zum `OnViewTest` an die Funktion zu implementieren:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#43](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_2.cpp)]  
  
### <a name="to-display-a-modeless-dialog-box"></a>Ein nicht modales Dialogfeld angezeigt.  
  
1.  Führen Sie die ersten vier Schritte, um ein modales Dialogfeld, außer die Ansichtsklasse (CDisplayDialogView) Wählen Sie in Schritt 4 angezeigt.  
  
2.  Bearbeiten Sie DisplayDialogView.h:  
  
    -   Deklarieren Sie die Dialogfeldklasse, die vor der Deklaration der ersten Klasse:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#44](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_3.h)]  
  
    -   Deklarieren Sie einen Zeiger auf das Dialogfeld nach dem öffentlichen Abschnitt "Attribute":  
  
         [!code-cpp[NVC_MFCControlLadenDialog#45](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_4.h)]  
  
3.  Bearbeiten Sie DisplayDialogView.cpp:  
  
    -   Fügen Sie die folgende Anweisung einschließen nach den vorhandenen #include-Anweisungen hinzu:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#42](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_1.cpp)]  
  
    -   Fügen Sie den folgenden Code an den Konstruktor:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#46](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_5.cpp)]  
  
    -   Fügen Sie den folgenden Code, auf den Destruktor:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#47](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_6.cpp)]  
  
    -   Fügen Sie folgenden Code zum `OnViewTest` an die Funktion zu implementieren:  
  
         [!code-cpp[NVC_MFCControlLadenDialog#48](../mfc/codesnippet/cpp/example-displaying-a-dialog-box-via-a-menu-command_7.cpp)]  
  
 Darüber hinaus finden Sie im folgenden Knowledge Base-Artikel:  
  
-   Q251059: So wird's gemacht: Geben Sie eine eigene Klasse Fenstername für MFC-Dialogfeld  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Modale und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)

