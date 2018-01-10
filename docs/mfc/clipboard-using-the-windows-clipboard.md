---
title: 'Zwischenablage: Verwenden der Windows-Zwischenablage | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Clipboard commands
- Cut/Copy and Paste command handler functions [MFC]
- handler functions, Cut/Copy and Paste commands
- Clipboard [MFC], commands
- commands [MFC], implementing Edit
- Clipboard commands [MFC], implementing
- Windows Clipboard [MFC]
- Clipboard [MFC], Windows Clipboard API
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6063a27495d46e4b54f3133b92689e4b0faaa631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clipboard-using-the-windows-clipboard"></a>Zwischenablage: Verwenden der Windows-Zwischenablage
In diesem Thema wird beschrieben, wie der standardmäßigen Windows-Zwischenablage-API in der MFC-Anwendung verwendet wird.  
  
 Die meisten Anwendungen für Windows unterstützen Ausschneiden oder Kopieren von Daten in die Windows-Zwischenablage und das Einfügen von Daten aus der Zwischenablage. Die zwischenablagedatenformate unterschiedlich von Anwendungen ab. Das Framework unterstützt nur eine begrenzte Anzahl von Zwischenablageformate für eine begrenzte Anzahl von Klassen. Normalerweise implementieren Sie die Zwischenablage-bezogenen Befehlen – Ausschneiden, kopieren und Einfügen – für die Ansicht im Menü Bearbeiten. Die Klassenbibliothek definiert die Befehls-IDs für diese Befehle: **ID_EDIT_CUT**, **ID_EDIT_COPY**, und **ID_EDIT_PASTE**. Ihre Nachricht-Line-Anweisungen sind auch definiert.  
  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md) wird erläutert, wie Befehle im Menü in der Anwendung zu behandeln, indem Sie eine Handlerfunktion des Menübefehls zuordnen. Solange der Anwendung nicht Handlerfunktionen für die zwischenablagebefehle im Menü Bearbeiten definiert ist, bleiben sie deaktiviert. Implementieren Sie zum Schreiben von Handlerfunktionen für die Befehle zum Ausschneiden und kopieren Auswahl in der Anwendung ein. Fragen Sie zum Schreiben einer Ereignishandler-Funktion für den Befehl Einfügen der Zwischenablage, um festzustellen, ob sie Daten in einem Format enthält, die Ihre Anwendung annehmen kann. Z. B., um den Kopierbefehl aktivieren können Sie einem Handler etwa wie folgt schreiben:  
  
 [!code-cpp[NVC_MFCListView#2](../atl/reference/codesnippet/cpp/clipboard-using-the-windows-clipboard_1.cpp)]  
  
 Die Befehle zum Ausschneiden, kopieren und Einfügen sind nur in bestimmten Kontexten Bedeutung. Die Befehle zum Ausschneiden und kopieren sollte aktiviert werden, nur, wenn ein Element ausgewählt ist und der Paste-Befehl nur dann, wenn etwas in der Zwischenablage ist. Sie können dieses Verhalten angeben, durch die Definition von Update Handlerfunktionen verknüpft die aktivieren oder deaktivieren diese Befehle je nach Kontext. Weitere Informationen finden Sie unter [wie Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md).  
  
 Die Microsoft Foundation Class-Bibliothek bietet Unterstützung der Zwischenablage zum Bearbeiten von Text mit der `CEdit` und `CEditView` Klassen. Die OLE-Klassen vereinfachen auch implementierende Zwischenablageoperationen, die OLE-Elemente einschließen. Weitere Informationen zu den OLE-Klassen finden Sie unter [Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 Implementieren anderer bearbeiten Menübefehlen, z. B. Rückgängig (**ID_EDIT_UNDO**) und Wiederherstellen (**ID_EDIT_REDO**), wird Ihnen auch Links. Wenn Ihre Anwendung diese Befehle nicht unterstützt, können Sie einfach aus der Ressourcendatei mit der Visual C++-Ressourcen-Editoren löschen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Verwenden des OLE-zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zwischenablage](../mfc/clipboard.md)

