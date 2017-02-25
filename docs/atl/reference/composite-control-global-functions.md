---
title: "Composite Control Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zusammengesetzte Steuerelemente, Globale Funktionen"
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Composite Control Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen bieten Unterstützung für das Erstellen von Dialogfeldern und zum Erstellen, das Hosten und Lizenzierung von ActiveX\-Steuerelementen.  
  
> [!IMPORTANT]
>  Die Funktionen, die in der folgenden Tabelle aufgeführt sind, können nicht in Anwendungen verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
|||  
|-|-|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Stellt ein modales Dialogfeld aus einer Dialogfeldvorlage erstellt, die vom Benutzer bereitgestellt wird.  Das resultierende Dialogfeld kann ActiveX\-Steuerelemente enthalten.|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Stellt ein nicht modales Dialogfeld aus einer Dialogfeldvorlage erstellt, die vom Benutzer bereitgestellt wird.  Das resultierende Dialogfeld kann ActiveX\-Steuerelemente enthalten.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Erstellt ein ActiveX\-Steuerelement, initialisiert und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Erstellt ein ActiveX\-Steuerelement, initialisiert es hostet, es im angegebenen Fenster und ruft einen Schnittstellenzeiger \(oder Zeiger\) aus dem Steuerelement ab.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger \(oder Zeiger\) aus dem Steuerelement ab.|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Fügt ein zuvor erstelltes Steuerelement zum angegebenen Fenster an.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Wird verwendet, um ein direkter Schnittstellenzeiger auf den Container für ein bestimmtes Fenster zu erhalten \(falls vorhanden\), das Handle angegeben.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Wird verwendet, um ein direkter Schnittstellenzeiger an das Steuerelement enthaltenen in zum Abrufen eines angegebenen Fenster \(falls vorhanden\), das Handle angegeben.|  
|[AtlSetChildSite](../Topic/AtlSetChildSite.md)|Initialisiert **IUnknown** der untergeordneten Site.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Initialisiert den Hostcode für AxWin\-Objekte.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Deinitialisiert den Hostcode für AxWin\-Objekte.|  
|[AtlGetObjectSourceInterface](../Topic/AtlGetObjectSourceInterface.md)|EINGABETASTEinformationen zu den Quellschnittstelle eines Objekts.|  
  
## Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Composite Control Macros](../../atl/reference/composite-control-macros.md)