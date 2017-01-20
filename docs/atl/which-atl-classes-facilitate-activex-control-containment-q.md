---
title: "Which ATL Classes Facilitate ActiveX Control Containment?"
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
  - "ActiveX-Steuerelementcontainer [C++], ATL control hosting"
  - "hosting controls using ATL"
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Which ATL Classes Facilitate ActiveX Control Containment?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Code SteuerelementHosting ATL erfordert, dass Sie keine ATL\-Klassen verwendet; Sie können ein **"AtlAxWin80"** Fenster einfach erstellen und das SteuerelementHosting API ggf. verwenden \(weitere Informationen finden Sie unter, [Was ist das ATL\-Steuerelement\-Hosting API?](../atl/what-is-the-atl-control-hosting-api-q.md)\).  jedoch machen die folgenden Klassen die Kapselungsfunktionen einfacher zu verwenden.  
  
|Klasse|Description|  
|------------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Umschließt ein **"AtlAxWin80"** Fenster ein und stellt Methoden zum Erstellen des Fensters, das Erstellen eines Steuerelements und\/oder das Anfügen eines Steuerelements in das Fenster und das Abrufen von Schnittstellenzeigern auf dem Hostobjekt bereit.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Umschließt ein **"AtlAxWinLic80"** Fenster ein und stellt Methoden zum Erstellen des Fensters, das Erstellen eines Steuerelements und\/oder das Anfügen eines Steuerelements lizenzierten in das Fenster und das Abrufen von Schnittstellenzeigern auf dem Hostobjekt bereit.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Tritt als eine Basisklasse für ActiveX\-Steuerelement\-Klassen auf Grundlage einer Dialogfeldressource auf.  Solche Steuerelemente können andere ActiveX\-Steuerelemente enthalten.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Tritt als eine Basisklasse für Dialogfeldklassen auf Grundlage einer Dialogfeldressource auf.  Solche Dialogfelder können ActiveX\-Steuerelemente enthalten.|  
|[CWindow](../atl/reference/cwindow-class.md)|Stellt eine Methode, [GetDlgControl](../Topic/CWindow::GetDlgControl.md), das einen Schnittstellenzeiger für ein Steuerelement zurückgibt, die ID des zugehörigen Hostfensters angegeben bereit.  Darüber hinaus machen die Windows\-API\-Wrapper, die von `CWindow` verfügbar gemacht werden im Allgemeinen, Fensterverwaltung einfacher.|  
  
## Siehe auch  
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)