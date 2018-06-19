---
title: Zuordnen von Meldungen zu Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3388cd8e9a52ef9aacb427d66b027d793b08ca75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371633"
---
# <a name="mapping-messages-to-functions"></a>Zuordnen von Meldungen zu Funktionen
Im Eigenschaftenfenster können Sie Meldungshandler (Memberfunktionen der MFC-Benutzeroberflächen-Klassen) zu binden, die Nachrichten, die durch die Ressourcen der Anwendung generiert. Verwenden sie [MFC-meldungszuordnungen](../../mfc/messages-and-commands-in-the-framework.md) , die Bindung zu erstellen.  
  
 Wenn Sie Klassenansicht verwenden, um eine neue von einer der Frameworkklassen abgeleitete Klasse zu erstellen, wird automatisch Klasse stellen einen vollständigen und funktionalen in den Headerdateien (. h) und die Implementierungsdatei (.cpp) Dateien, die Sie angeben.  
  
> [!NOTE]
>  Um eine neue Klasse hinzufügen, die diese Nachrichten nicht verarbeiten kann, erstellen Sie die Klasse direkt in den Text-Editor ein.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>So definieren oder Entfernen eines meldungshandlers mithilfe des Eigenschaftenfensters  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Nachrichten** Schaltfläche.  
  
    > [!NOTE]
    >  Die **Nachrichten** Schaltfläche ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht oder im Quellcodefenster auf auswählen.  
  
     Wenn das Projekt einen Handler für eine Nachricht hat, wird der Name des Handlers in der rechten Spalte neben der Nachricht angezeigt.  
  
3.  Wenn die Nachricht keinen Ereignishandler aufweist, klicken Sie dann auf die Zelle in der rechten Spalte im Fenster Eigenschaften den vorgeschlagenen Namen des Handlers als anzuzeigende \<hinzufügen >*HandlerName*. (Z. B. die `WM_TIMER` Meldungshandler schlägt \<hinzufügen >`OnTimer`).  
  
4.  Klicken Sie auf den vorgeschlagenen Namen Stubcode für die Funktion hinzufügen.  
  
5.  Um einen Meldungshandler zu bearbeiten, doppelklicken Sie auf die Nachricht in der Klassenansicht und bearbeiten Sie den Code im Quellcodefenster.  
  
 Um einen Meldungshandler zu entfernen, doppelklicken Sie auf den Handler in der rechten Spalte aus, und wählen Sie \<Löschen >*HandlerName*. Der Code der Funktion wird auskommentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)
