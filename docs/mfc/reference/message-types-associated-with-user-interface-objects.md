---
title: Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.uiobject.msgs
dev_langs:
- C++
helpviewer_keywords:
- message types and user interface objects [MFC]
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a2309556ca6c5204247ccbe916aebe472a1da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="message-types-associated-with-user-interface-objects"></a>Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen
Die folgende Tabelle zeigt die Typen von Objekten, mit denen Sie arbeiten, und den Nachrichtentypen zugeordnet.  
  
### <a name="user-interface-objects-and-associated-messages"></a>Benutzeroberflächenobjekte und zugeordneten Nachrichten  
  
|Objekt-ID|Mitteilungen|  
|---------------|--------------|  
|Klassennamen, die des enthaltenden Fensters darstellt.|Windows-Meldungen gemäß einer [CWnd](../../mfc/reference/cwnd-class.md)-abgeleitete Klasse: ein Dialogfeld, Fenster, untergeordnetes Fenster, untergeordnetes MDI-Fenster oder Rahmenfenster der obersten Ebene.|  
|Menü oder die Tastenkombination Bezeichner|-   **Befehl** Nachricht (die Programmfunktion ausgeführt).<br />-   **UPDATE_COMMAND_UI** Nachricht (dynamisch aktualisiert das Menüelement).|  
|Steuerelement-ID|Benachrichtigungsmeldungen des Registersteuerelements für den ausgewählten Steuerelementtyp.|  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)
