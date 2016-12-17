---
title: "IAxWinHostWindow Interface"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindow interface"
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindow Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Schnittstelle stellt Methoden zum Bearbeiten eines Steuerelements und seines Hostobjekts bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
interface IAxWinHostWindow : IUnknown  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[AttachControl](../Topic/IAxWinHostWindow::AttachControl.md)|Fügt ein vorhandenes Steuerelement an das Hostobjekt an.|  
|[CreateControl](../Topic/IAxWinHostWindow::CreateControl.md)|Erstellt ein und fügt es dem Steuerelement Hostobjekt an.|  
|[CreateControlEx](../Topic/IAxWinHostWindow::CreateControlEx.md)|Erstellt ein Steuerelement, fügt das Hostobjekt an installiert und optional einen Ereignishandler.|  
|[QueryControl](../Topic/IAxWinHostWindow::QueryControl.md)|Gibt einen Schnittstellenzeiger an das gehostete Steuerelement zurück.|  
|[SetExternalDispatch](../Topic/IAxWinHostWindow::SetExternalDispatch.md)|Legt die externe `IDispatch`\-Schnittstelle fest.|  
|[SetExternalUIHandler](../Topic/IAxWinHostWindow::SetExternalUIHandler.md)|Legt die externe `IDocHostUIHandlerDispatch`\-Schnittstelle fest.|  
  
## Hinweise  
 Diese Schnittstelle wird von ATL ActiveX\-Steuerelement verfügbar gemacht, das Objekte hostet.  Rufen Sie die Methoden für diese Schnittstelle auf, um ein Steuerelement auf das Hostobjekt zu erstellen und\/oder anzufügen, um eine Schnittstelle von einem gehosteten Steuerelement abzurufen, oder die externe Dispatchschnittstelle oder Benutzeroberfläche\-Handler zur Verwendung festzulegen, wenn Sie den Webbrowser hosten.  
  
## Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL\-Datei oder C\+\+, wie unten verfügbar.  
  
|Definitionstyp|Datei|  
|--------------------|-----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(auch enthaltene ATLBase.h\)|  
  
## Siehe auch  
 [IAxWinAmbientDispatch Interface](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)