---
title: "Definieren eines Meldungshandlers f&#252;r eine reflektierte Meldung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.defining.msg.msghandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungsbehandlung, Reflektierte Meldungen"
  - "Meldungen, Reflektiert"
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Definieren eines Meldungshandlers f&#252;r eine reflektierte Meldung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie eine neue MFC\-Steuerelementklasse erstellt haben, können Sie Meldungshandler für die Klasse definieren.  Über Handler für reflektierte Meldungen können Steuerelementklassen eigene Meldungen verarbeiten, bevor das übergeordnete Fenster die Meldung empfängt.  Sie können die MFC\-Funktion [CWnd::SendMessage](../Topic/CWnd::SendMessage.md) verwenden, um Meldungen vom Steuerelement an ein übergeordnetes Fenster zu übertragen.  
  
 Mit dieser Funktionalität könnten Sie beispielsweise ein Listenfeld erstellen, das sich selbst neu zeichnet und nicht darauf wartet, dass es vom übergeordneten Fenster \(Besitzer\) neu gezeichnet wird.  Weitere Informationen zu reflektierten Meldungen finden Sie unter [Behandeln von reflektierten Meldungen](../../mfc/handling-reflected-messages.md).  
  
 Um ein [ActiveX\-Steuerelement](../../mfc/activex-controls-on-the-internet.md) mit derselben Funktionalität anzulegen, müssen Sie ein Projekt für das ActiveX\-Steuerelement erstellen.  
  
> [!NOTE]
>  Reflektierte Meldungen \(OCM\_*Message*\) können einem ActiveX\-Steuerelement nicht im Eigenschaftenfenster hinzugefügt werden, wie dies im Folgenden für andere Meldungen beschrieben wird.  Diese Meldungen müssen manuell hinzugefügt werden.  
  
### So definieren Sie im Eigenschaftenfenster einen Meldungshandler für eine reflektierte Meldung  
  
1.  Fügen Sie dem MFC\-Projekt ein Steuerelement hinzu, z. B. eine Liste, eine Infoleiste, eine Symbolleiste oder eine Strukturansicht.  
  
2.  Klicken Sie in der Klassenansicht auf den Namen der Steuerelementklasse.  
  
3.  Der Name der Steuerelementklasse wird im [Eigenschaftenfenster](../Topic/Properties%20Window.md) in der Liste **Klassenname** angezeigt.  
  
4.  Klicken Sie auf die Schaltfläche **Meldungen**, um die Windows\-Meldungen anzuzeigen, die dem Steuerelement hinzugefügt werden können.  
  
5.  Führen Sie im Eigenschaftenfenster in der Meldungsliste einen Bildlauf nach unten durch, bis Sie die Überschrift **Reflektiert** sehen.  Alternativ können Sie auf die Schaltfläche **Kategorien** klicken und die Ansicht reduzieren, um die Überschrift **Reflektiert** anzeigen zu lassen.  
  
6.  Wählen Sie die reflektierte Meldung aus, für die Sie einen Handler definieren möchten.  Die reflektierten Meldungen sind durch ein Gleichheitszeichen \(\=\) gekennzeichnet.  
  
7.  Klicken Sie auf die Zelle in der rechten Spalte des Eigenschaftenfensters, um den vorgeschlagenen Namen des Handlers als \<addHandlerName\>anzuzeigen. \(Beispielweise, schlägt \<der **\=WM\_CTLCOLOR** Meldungshandler hinzufügen \>**CtlColor** vor\).  
  
8.  Klicken Sie auf den vorgeschlagenen Namen, um ihn zu bestätigen.  Der Handler wird dem Projekt hinzugefügt.  
  
     Die Namen der hinzugefügten Meldungshandler werden in der rechten Spalte des Fensters für reflektierte Meldungen angezeigt.  
  
9. Um einen Meldungshandler zu bearbeiten oder zu löschen, wiederholen Sie die Schritte 4 bis 7.  Klicken Sie auf die Zelle, die den zu bearbeitenden oder zu löschenden Handlernamen enthält, und klicken Sie dann auf die entsprechende Task.  
  
## Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)