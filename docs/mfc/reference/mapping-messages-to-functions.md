---
title: Zuordnen von Meldungen zu Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [C++], adding message handlers
- message maps [C++], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 584cc8b1f59f94d88718add5c21046c487b8556f
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="mapping-messages-to-functions"></a>Zuordnen von Meldungen zu Funktionen
Im Eigenschaftenfenster können Sie Meldungshandler (Memberfunktionen der MFC-Benutzeroberflächen-Klassen) zu binden, die durch die Ressourcen der Anwendung generierten Nachrichten. Verwenden sie [MFC-meldungszuordnungen](../../mfc/messages-and-commands-in-the-framework.md) , die Bindung zu erstellen.  
  
 Wenn Sie die Klassenansicht verwenden, erstellen Sie eine neue Klasse, die von einer der Framework-Klassen abgeleitet werden, wird automatisch Klasse stellen eine vollständige und funktionale in der Headerdatei (.h) und die Implementierungsdatei (.cpp)-Dateien, die Sie angeben.  
  
> [!NOTE]
>  Erstellen Sie die Klasse direkt in den Text-Editor, um eine neue Klasse hinzuzufügen, die Nachrichten nicht behandelt.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>So definieren oder entfernen einen Meldungshandler im Eigenschaftenfenster  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Fenster Eigenschaften auf die **Nachrichten** Schaltfläche.  
  
    > [!NOTE]
    >  Die **Nachrichten** Schaltfläche ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht oder im Quellcodefenster auf auswählen.  
  
     Wenn das Projekt einen Handler für eine Meldung verfügt, wird der Name den Handler in der rechten Spalte neben der Nachricht angezeigt.  
  
3.  Wenn die Meldung kein Handler verfügbar ist, klicken Sie dann auf die Zelle in der rechten Spalte im Fenster Eigenschaften auf den vorgeschlagenen Namen den Handler als anzeigen \<hinzufügen >*HandlerName*. (Z. B. die `WM_TIMER` Meldungshandler schlägt \<hinzufügen >`OnTimer`).  
  
4.  Klicken Sie auf den vorgeschlagenen Namen Stubcode für die Funktion hinzufügen.  
  
5.  Um einen Meldungshandler zu bearbeiten, doppelklicken Sie auf die Nachricht in der Klassenansicht und bearbeiten Sie den Code im Quellcodefenster.  
  
 Um einen Meldungshandler zu entfernen, doppelklicken Sie auf die Handler in der rechten Spalte, und wählen Sie \<löschen >*HandlerName*. Der Funktionscode wird auskommentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)

