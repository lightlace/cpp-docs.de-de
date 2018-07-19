---
title: Zuordnen von Meldungen zu Funktionen | Microsoft-Dokumentation
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
ms.openlocfilehash: 962a86139b7fdf8afac08e04e7b42240603b4374
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335525"
---
# <a name="mapping-messages-to-functions"></a>Zuordnen von Meldungen zu Funktionen
Das Fenster "Eigenschaften" können Sie Meldungshandler (Memberfunktionen der MFC-Benutzeroberflächen-Klassen) zu binden, um die Nachrichten, die von Ihrer Anwendung Ressourcen generiert werden. Sie verwenden [MFC-meldungszuordnungen](../../mfc/messages-and-commands-in-the-framework.md) , die Bindung zu erstellen.  
  
 Wenn Sie die Klassenansicht verwenden, erstellen Sie eine neue Klasse, die von einer der Framework-Klassen abgeleitet, wird automatisch Klasse stellen eine vollständige und funktionale in den Headerdateien (h) und der Implementierungsdatei (.cpp) Dateien, die Sie angeben.  
  
> [!NOTE]
>  Um eine neue Klasse hinzufügen, die Nachrichten nicht behandelt, erstellen Sie die Klasse direkt im Text-Editor ein.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Um zu definieren, oder entfernen ein meldungshandlers mithilfe des Eigenschaftenfensters  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die **Nachrichten** Schaltfläche.  
  
    > [!NOTE]
    >  Die **Nachrichten** Schaltfläche ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht oder im Quellcodefenster auf auswählen.  
  
     Wenn Ihr Projekt einen Handler für eine Nachricht verfügt, wird der Name des Handlers in der rechten Spalte neben der Meldung angezeigt.  
  
3.  Wenn die Nachricht kein Handler verfügt, klicken Sie dann auf die Zelle in der rechten Spalte im Fenster Eigenschaften den vorgeschlagenen Namen des Handlers als anzuzeigende \<hinzufügen >*HandlerName*. (Z. B. der WM_TIMER Meldungshandler schlägt \<hinzufügen >`OnTimer`).  
  
4.  Klicken Sie auf den empfohlenen Namen, um Stubcode für die Funktion hinzuzufügen.  
  
5.  Klicken Sie zum Bearbeiten eines meldungshandlers Doppelklicken Sie auf die Nachricht in der Klassenansicht, und bearbeiten Sie den Code im Quellcodefenster.  
  
 Um einen Meldungshandler entfernen möchten, doppelklicken Sie auf den Handler in der rechten Spalte aus, und wählen Sie \<Löschen >*HandlerName*. Der Code der Funktion wird auskommentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC Message Handler (MFC-Meldungshandler)](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding a Class (Hinzufügen einer Klasse)](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Adding a Member Variable (Hinzufügen einer Membervariablen)](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Navigating the Class Structure (Navigieren in der Klassenstruktur)](../../ide/navigating-the-class-structure-visual-cpp.md)
