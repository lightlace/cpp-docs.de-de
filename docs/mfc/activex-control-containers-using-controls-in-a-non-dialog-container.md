---
title: "ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind"
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
  - "ActiveX-Steuerelementcontainer [C++], Einfügen von Steuerelementen"
  - "ActiveX-Steuerelementcontainer [C++], non-dialog-Container"
  - "ActiveX-Steuerelemente [C++], Erstellen"
  - "Create-Methode [C++], ActiveX-Steuerelemente"
  - "CreateControl-Methode"
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einigen Anwendungen wie einer SDI\- oder MDI\-Anwendung, möchten Sie ein Steuerelement in einem Fenster der Anwendung einbetten.  Die **Erstellen**\-Memberfunktion der Wrapperklasse, eingefügt von Visual C\+\+, können eine Instanz des Steuerelements, ohne die Anforderung ein Dialogfeld dynamisch erstellen.  
  
 Die **Erstellen**\-Memberfunktion besitzt die folgenden Parameter:  
  
 `lpszWindowName`  
 Ein Zeiger in der Text\- oder Beschriftungseigenschaft anzuzeigende Text, des Steuerelements \(falls vorhanden\).  
  
 `dwStyle`  
 Windows\-Formate.  Eine vollständige Liste finden Sie unter [CWnd::CreateControl](../Topic/CWnd::CreateControl.md).  
  
 `rect`  
 Gibt die Größe und Position des Steuerelements an.  
  
 `pParentWnd`  
 Gibt dem übergeordneten Fenster des Steuerelements, normalerweise `CDialog` an.  Darf nicht **NULL** sein.  
  
 `nID`  
 Gibt die Steuerelement\-ID an und kann über den Container verwendet werden, um das Steuerelement zu verweisen.  
  
 Ein Beispiel für die Verwendung dieser Funktion, um ein ActiveX\-Steuerelement dynamisch erzeugen kann in einer Formularansicht einer SDI\-Anwendung sein.  Sie können eine Instanz des Steuerelements im `WM_CREATE`\-Handler der Anwendung erstellen.  
  
 Für dieses Beispiel ist `CMyView` die Hauptansichtsklasse, ist `CCirc` die Wrapperklasse, und CIRC.H ist den Header \(.H\) Datei der Wrapperklasse.  
  
 Diese Funktion zu implementieren ist ein vier Schritte.  
  
### So fügen Sie ein ActiveX\-Steuerelement in einem NichtDialogfeldfenster dynamisch erstellen  
  
1.  Fügen Sie CIRC.H in CMYVIEW.H, direkt vor der Klassendefinition ein: `CMyView`  
  
     [!CODE [NVC_MFC_AxCont#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#12)]  
  
2.  Fügen Sie eine Membervariable \(vom Typ `CCirc`\) des geschützten Abschnitt der `CMyView` in CMYVIEW.H Klassendefinition hinzu:  
  
     [!CODE [NVC_MFC_AxCont#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#13)]  
    [!CODE [NVC_MFC_AxCont#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#14)]  
  
3.  Fügen Sie `WM_CREATE` einen Meldungshandler hinzu, um `CMyView`\- Klasse.  
  
4.  In die Handlerfunktion machen `CMyView::OnCreate`, einen Aufruf der `Create`\-Funktion des Steuerelements mithilfe des **this** \- Zeigers als übergeordnetes Fenster:  
  
     [!CODE [NVC_MFC_AxCont#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#15)]  
  
5.  Erstellen Sie das Projekt neu.  Ein Circ\-Steuerelement wird dynamisch erstellt, wenn die Ansicht der Anwendung erstellt wird.  
  
## Siehe auch  
 [ActiveX\-Steuerelementcontainer](../mfc/activex-control-containers.md)