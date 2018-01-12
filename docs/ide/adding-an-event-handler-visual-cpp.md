---
title: "Hinzufügen eines Ereignishandlers (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>Hinzufügen eines Ereignishandlers (Visual C++)
Aus dem Ressourcen-Editor können Sie einen neuen Ereignishandler hinzufügen oder bearbeiten Sie einen vorhandenen Ereignishandler für ein Dialogfeld Steuerelement unter Verwendung der [Ereignishandler-Assistent](../ide/event-handler-wizard.md).  
  
 Fügen Sie ein Ereignis, um die Klasse zur Implementierung des Dialogfelds mit den [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Wenn Sie das Ereignis auf einer anderen Klasse als der Dialogfeldklasse hinzufügen möchten, verwenden Sie die Ereignishandler-Assistent.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Ein Dialogfeld-Steuerelement einen Ereignishandler hinzu  
  
1.  Doppelklicken Sie auf die Dialogfeldressource in [Ressourcenansicht](../windows/resource-view-window.md) die Dialogfeldressource öffnen, mit dem Steuerelement in der [Dialog-Editor](../windows/dialog-editor.md).  
  
2.  Mit der rechten Maustaste in des Steuerelements das Benachrichtigungsereignis behandelt werden soll.  
  
3.  Klicken Sie im Kontextmenü auf **Ereignishandler hinzufügen** die Ereignishandler-Assistent angezeigt.  
  
4.  Wählen Sie das Ereignis in der **Nachrichtentyp** Feld der Klasse, die im ausgewählten Hinzufügen der **Klassenliste** Feld.  
  
5.  Übernehmen Sie den Standardnamen in der **Handler Funktionsnamen** ein, oder geben Sie den Namen Ihrer Wahl.  
  
6.  Klicken Sie auf **hinzufügen und bearbeiten** fügen den Ereignishandler für das Projekt, und öffnen Sie den Texteditor an der neuen Funktion zum Hinzufügen des entsprechenden Ereignishandlercode.  
  
     Wenn die ausgewählten Nachrichtentyp einen Ereignishandler für die ausgewählte Klasse bereits **hinzufügen und bearbeiten** nicht verfügbar ist, und **Code bearbeiten** verfügbar ist. Klicken Sie auf **Code bearbeiten** Text-Editor an der vorhandenen Funktion zu öffnen.  
  
 Alternativ können Sie Ereignishandler von Hinzufügen der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Finden Sie unter [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)