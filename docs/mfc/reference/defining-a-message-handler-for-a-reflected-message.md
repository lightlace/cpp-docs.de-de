---
title: "Definieren einen Meldungshandler für eine reflektierte Meldung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages, reflected
- message handling, reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0033c75d351aa201a0c18e81395d764b9d45761b
ms.lasthandoff: 02/24/2017

---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Definieren eines Meldungshandlers für eine reflektierte Meldung
Sobald Sie eine neue MFC-Steuerelementklasse erstellt haben, können Sie Meldungshandler dafür definieren. Reflektierte Meldung-Handler können eine Klasse eigene Nachrichten zu verarbeiten, bevor die Nachricht vom übergeordneten Element empfangen wurde. Sie können die MFC-Bibliothek [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) Funktion zum Senden von Nachrichten über das Steuerelement an ein übergeordnetes Fenster.  
  
 Erstellen Sie mit dieser Funktionalität Sie z. B. könnten ein Listenfeld, das sich selbst neu gezeichnet wird, statt auf das übergeordnete Fenster (Besitzer gezeichnet) möchten. Weitere Informationen zu reflektierte Nachrichten finden Sie unter [reflektiert Nachrichten Behandeln von](../../mfc/handling-reflected-messages.md).  
  
 Erstellen einer [ActiveX-Steuerelement](../../mfc/activex-controls-on-the-internet.md) mit den gleichen Funktionen müssen Sie ein Projekt für das ActiveX-Steuerelement erstellen.  
  
> [!NOTE]
>  Sie können keine reflektierte Meldung hinzufügen (OCM*Nachricht*) mithilfe des Eigenschaftenfensters für ein ActiveX-steuern, wie unten beschrieben. Diese Nachrichten müssen Sie manuell hinzufügen.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Um einen Meldungshandler für eine reflektierte Meldung im Fenster Eigenschaften zu definieren.  
  
1.  Fügen Sie dem MFC-Projekt ein Steuerelement, z. B. eine Liste, einem Grundleisten-Steuerelement, eine Symbolleiste oder ein Strukturansicht-Steuerelement hinzu.  
  
2.  Klicken Sie in der Klassenansicht auf den Namen der Steuerelementklasse.  
  
3.  In der [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window), der Name der Steuerelementklasse wird angezeigt, der **Klassenname** Liste.  
  
4.  Klicken Sie auf die **Nachrichten** Schaltfläche, um die Anzeige der Windows-Meldungen, die auf dem Steuerelement hinzugefügt.  
  
5.  Bildlauf nach unten in der Liste der Nachrichten im Fenster "Eigenschaften", bis Sie die Überschrift anzuzeigen, **reflektiert**. Klicken Sie alternativ auf die **Kategorien** Schaltfläche und die Ansicht reduzieren, finden Sie unter der **reflektiert** Überschrift.  
  
6.  Wählen Sie die reflektierte Meldung für die Sie einen Handler definieren möchten. Reflektierte Meldungen werden mit einem Gleichheitszeichen (=) gekennzeichnet.  
  
7.  Klicken Sie auf die Zelle in der rechten Spalte im Fenster Eigenschaften auf den vorgeschlagenen Namen den Handler als anzeigen \<hinzufügen >*HandlerName*. (Z. B. die **= WM_CTLCOLOR** Meldungshandler schlägt \<hinzufügen >**CtlColor vor**).  
  
8.  Klicken Sie auf den vorgeschlagenen Namen zu akzeptieren. Der Handler wird dem Projekt hinzugefügt.  
  
     Message-Handler-Namen, die Sie hinzugefügt haben angezeigt, in der rechten Spalte des Fensters reflektierte Meldungen  
  
9. Zum Bearbeiten oder Löschen einen Meldungshandler, wiederholen Sie die Schritte 4 bis 7. Klicken Sie auf die Zelle mit dem Handlernamen bearbeiten oder löschen, und klicken Sie auf die entsprechende Aufgabe.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)

