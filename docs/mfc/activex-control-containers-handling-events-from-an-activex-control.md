---
title: "ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++], Ereignissenken"
  - "ActiveX-Steuerelemente [C++], Ereignisse"
  - "BEGIN_EVENTSINK_MAP-Makro"
  - "END_EVENTSINK_MAP-Makro, Verwenden"
  - "Ereignishandler [C++], ActiveX-Steuerelemente"
  - "Ereignisbehandlung [C++], ActiveX-Steuerelemente"
  - "Ereignisse [C++], ActiveX-Steuerelemente"
  - "ON_EVENT-Makro"
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Behandeln von Ereignissen eines ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden mithilfe des Eigenschaftenfensters, um Ereignishandler für ActiveX\-Steuerelemente in ein ActiveX\-Steuerelementcontainer zu installieren.  Die Ereignishandler werden verwendet, um Benachrichtigungen \(vom Steuerelement\) über bestimmte Ereignisse empfängt und eine Aktion in der Antwort auszuführen.  Diese Benachrichtigung wird "Auslösen" des Ereignisses aufgerufen.  
  
> [!NOTE]
>  Dieser Artikel wird ein auf Dialogfeldern basierenden ActiveX\-Steuerelementcontainer Projekt benannten Container ein eingebettetes Steuerelement, das Circ als Beispiele in den Prozeduren und im Code ".  
  
 Mit der Schaltfläche Ereignisse Sie im Eigenschaftenfenster, können Sie eine Zuordnung von Ereignissen erstellen, die in der ActiveX\-Steuerelement\-Containeranwendung auftreten können.  Diese Zuordnung, als "Ereignissenkenzuordnung," wird von Visual C\+\+ erstellt und verwaltet, wenn Sie der Steuerelementcontainerklasse Ereignishandler hinzufügen.  Jeder Ereignishandler implementiert, mit einem Ereigniszuordnungseintrag, ordnet einem bestimmten Ereignis an eine Containerereignishandlermemberfunktion zu.  Diese Ereignishandlerfunktion wird aufgerufen, wenn das angegebene Ereignis vom ActiveX\-Steuerelementobjekt ausgelöst wird.  
  
 Weitere Informationen über Ereignissenkenzuordnungen, finden Sie unter [Ereignissenkenzuordnungen](../mfc/reference/event-sink-maps.md) in der Class Library Reference.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a> Ereignishandler\-Änderungen zum Projekt  
 Wenn Sie das Eigenschaftenfenster verwenden, um Ereignishandler hinzuzufügen, wird eine Ereignissenkenzuordnung im Projekt deklariert und definiert.  Die folgenden Anweisungen werden zur Steuercpp\-datei hinzugefügt, wenn ein Ereignishandler hinzugefügt wird.  Dieser Code deklariert eine Ereignissenkenzuordnung für die Dialogfeldklasse \(in diesem Fall, `CContainerDlg`\):  
  
 [!CODE [NVC_MFC_AxCont#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#8)]  
[!CODE [NVC_MFC_AxCont#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#9)]  
  
 Während Sie das Eigenschaftenfenster verwenden, um Ereignisse hinzufügen möchten, ist ein Ereigniszuordnungseintrag \(`ON_EVENT`\) zur Ereignissenkenzuordnung und zu einem Ereignishandler hinzugefügt, die Funktion zur Implementierungsdatei des Containers \(.CPP\) hinzugefügt wird.  
  
 Das folgende Beispiel deklariert einen Ereignishandler, `OnClickInCircCtrl`, für das Circ\- **ClickIn**\-Ereignis des Steuerelements:  
  
 [!CODE [NVC_MFC_AxCont#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#10)]  
  
 Außerdem wird die folgende Vorlage der Datei `CContainerDlg` \(.CPP Klassenimplementierung\) für die Ereignishandlermemberfunktion hinzugefügt:  
  
 [!CODE [NVC_MFC_AxCont#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#11)]  
  
 Weitere Informationen über Ereignissenkenmakros, finden Sie unter [Ereignissenkenzuordnungen](../mfc/reference/event-sink-maps.md) in der Class Library Reference.  
  
#### Um eine Ereignishandlerfunktion erstellen  
  
1.  In der Klassenansicht die Dialogfeldklasse aus, die das ActiveX\-Steuerelement enthält.  Verwenden Sie beispielsweise `CContainerDlg`.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Ereignisse**.  
  
3.  Wählen Sie im Eigenschaftenfenster die Steuerelement\-ID des eingebetteten ActiveX\-Steuerelements aus.  Verwenden Sie beispielsweise `IDC_CIRCCTRL1`.  
  
     Das Eigenschaftenfenster zeigt eine Liste von Ereignissen an, die das ActiveX\-Steuerelement eingebettete ausgelöst werden können.  Jede Memberfunktion, die in Fettdruck wurde veranschaulicht wird bereits, die Handlerfunktionen, die an sie zugewiesen werden.  
  
4.  Wählen Sie das Ereignis aus, das Sie der Dialogfeldklasse behandeln soll.  In diesem Beispiel die Option **Klicken** aus.  
  
5.  Wählen Sie im Dropdown\-Listenfeld rechts, und wählen Sie **\<Add\> ClickCircctrl1** aus.  
  
6.  Doppelklicken Sie auf die neue Handlerfunktion von der Klassenansicht, um zum Ereignishandlercode in der Implementierungsdatei \(.CPP\) von `CContainerDlg` zu wechseln.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)