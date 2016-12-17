---
title: "What Is the ATL Control-Hosting API?"
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
  - "APIs [C++], Hosting"
  - "control-hosting API"
  - "Steuerelemente [ATL], Hosting-APIs"
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 15
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# What Is the ATL Control-Hosting API?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

SteuerelementHosting API ATL ist der Satz von Funktionen, der jedem Fenster ermöglicht, als ein ActiveX\-Steuerelementcontainer fungiert.  Diese Funktionen können in das Projekt statisch oder dynamisch zu verknüpfen, da sie als Quellcode verfügbar sind und von ATL90.dll verfügbar gemacht.  Die SteuerelementHosting Funktionen sind in der folgenden Tabelle aufgelistet.  
  
|Funktion|Description|  
|--------------|-----------------|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Erstellt ein Hostobjekt, schließt die an das angegebene Fenster, fügt dann ein vorhandenes Steuerelement an.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Erstellt ein Hostobjekt, schließt die an das angegebene Fenster, dann wird ein Steuerelement.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert und hostet es im angegebenen Fenster, das zu [AtlAxCreateControl](../Topic/AtlAxCreateControl.md) ähnelt.|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Erstellt ein Hostobjekt, schließt die an das angegebene Fenster, dann wird ein Steuerelement \(ermöglicht auch die installiert werden Ereignissenken,\).|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert und hostet es im angegebenen Fenster, das zu [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md) ähnelt.|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Stellt ein nicht modales Dialogfeld aus einer Dialogfeldressource erstellt und gibt das Fensterhandle zurück.|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Stellt ein modales Dialogfeld aus einer Dialogfeldressource erstellt.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Gibt den **IUnknown**\-Schnittstellenzeiger des Steuerelements zurück, die in einem Fenster gehostet wird.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Gibt den **IUnknown**\-Schnittstellenzeiger des Hostobjekts zurück, das an ein Fenster verbunden ist.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Initialisiert den SteuerelementHosting Code.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Deinitialisiert den SteuerelementHosting Code.|  
  
 Die `HWND`\-Parameter in den ersten drei Funktionen muss ein vorhandenes Fenster \(fast\) eines beliebigen Typs sein.  Wenn Sie alle drei Funktionen explizit \(in der Regel, sind Sie nicht müssen\), aufrufen, übergeben Sie ein Handle nicht zu einem Fenster, das bereits als Host fungiert \(wenn Sie ausführen, wird das vorhandene Hostobjekt nicht freigegeben\).  
  
 Der erste Aufruf [AtlAxWinInit](../Topic/AtlAxWinInit.md) mit sieben Funktionen implizit.  
  
> [!NOTE]
>  Das SteuerelementHosting API bildet die Grundlage Unterstützung ATL für ActiveX\-Steuerelement\-Kapselung.  Es gibt jedoch normalerweise wenig Anforderung, diese Funktionen direkt aufrufen, wenn Sie vollständigen Verwendung Wrapperklassen ATL nutzen oder ausführen.  Weitere Informationen finden Sie unter [Welche ATL klassifiziert erleichtert ActiveX\-Steuerelement\-Kapselung?](../atl/which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## Siehe auch  
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)