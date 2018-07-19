---
title: Definieren eines Meldungshandlers für eine reflektierte Meldung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed941816824c77f14a3364b06af0b3da171ee8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373168"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Definieren eines Meldungshandlers für eine reflektierte Meldung
Nachdem Sie eine neue MFC-Steuerelementklasse erstellt haben, können Sie Meldungshandler dafür definieren. Reflektierte fenstermeldungs-Handler ermöglichen die Steuerelementklasse eigene Nachrichten zu verarbeiten, bevor die Nachricht vom übergeordneten Element empfangen wird. Sie können die MFC-Bibliothek [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) Funktion zum Senden von Nachrichten über das Steuerelement für ein übergeordnetes Fenster.  
  
 Erstellen Sie mit dieser Funktionalität Sie z. B. könnten ein Listenfeld, das sich selbst neu zeichnet, wird anstatt auf das übergeordnete Fenster, ist dies der Fall ist (Ownerdrawn). Weitere Informationen zu reflektierte Meldungen, finden Sie unter [reflektiert Nachrichten behandeln](../../mfc/handling-reflected-messages.md).  
  
 Zum Erstellen einer [ActiveX-Steuerelement](../../mfc/activex-controls-on-the-internet.md) mit derselben Funktionalität, müssen Sie ein Projekt für das ActiveX-Steuerelement erstellen.  
  
> [!NOTE]
>  Eine reflektierte Meldung kann nicht hinzugefügt werden (OCM*Nachricht*) mithilfe des Eigenschaftenfensters für ein ActiveX-steuern, wie unten beschrieben. Diese Nachrichten müssen Sie manuell hinzufügen.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Zum Definieren eines meldungshandlers für eine reflektierte Meldung über das Eigenschaftenfenster  
  
1.  Fügen Sie dem MFC-Projekt ein Steuerelement, z. B. eine Liste, einem Grundleisten-Steuerelement, eine Symbolleiste oder ein Strukturansicht-Steuerelement hinzu.  
  
2.  Klicken Sie in der Klassenansicht auf den Namen der Steuerelementklasse.  
  
3.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), den Namen der Steuerelementklasse wird angezeigt, der **Klassenname** Liste.  
  
4.  Klicken Sie auf die **Nachrichten** Schaltfläche zur Anzeige der Windows-Meldungen, die auf dem Steuerelement hinzugefügt.  
  
5.  Blättern Sie in der Liste der Nachrichten im Eigenschaftenfenster angezeigt, bis Sie die Überschrift angezeigt **reflektiert**. Klicken Sie alternativ auf die **Kategorien** Schaltfläche und reduzieren Sie die Ansicht finden Sie unter der **reflektiert** Überschrift.  
  
6.  Wählen Sie die reflektierte Meldung für die Sie einen Ereignishandler definieren möchten. Reflektierte Meldungen werden mit einem Gleichheitszeichen (=) markiert.  
  
7.  Klicken Sie auf die Zelle in der rechten Spalte im Fenster Eigenschaften den vorgeschlagenen Namen des Handlers als anzuzeigende \<hinzufügen >*HandlerName*. (Z. B. die **= WM_CTLCOLOR** Meldungshandler schlägt \<hinzufügen >**CtlColor vor**).  
  
8.  Klicken Sie auf den vorgeschlagenen Namen zu akzeptieren. Der Handler wird dem Projekt hinzugefügt.  
  
     Nachricht Handlernamen, die Sie hinzugefügt haben, die in der rechten Spalte des Fensters reflektierte Meldungen angezeigt werden.  
  
9. Zum Bearbeiten oder Löschen eines meldungshandlers, wiederholen Sie die Schritte 4 bis 7. Klicken Sie auf die Zelle, den Handlernamen bearbeiten oder löschen, und klicken Sie auf die entsprechende Aufgabe.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)
