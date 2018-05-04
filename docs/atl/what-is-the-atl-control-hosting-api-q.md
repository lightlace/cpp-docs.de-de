---
title: Was ist die ATL-Steuerelement-Hosting-API? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30b104e21259006da41c236c168431d85b43e0d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="what-is-the-atl-control-hosting-api"></a>Was ist die ATL-Steuerelement-Hosting-API?
ATL des Steuerelements hosting-API ist der Satz von Funktionen, die einem beliebigen Fenster fungieren als ActiveX-Steuerelement-Container ermöglicht. Diese Funktionen können statisch oder dynamisch in das Projekt eingebunden werden, da sie als Quellcode verfügbar sind und von ATL90.dll verfügbar gemacht werden. Das Hosten von Steuerelementen Funktionen werden in der folgenden Tabelle aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Erstellt ein Hostobjekt, verbindet ihn mit dem bereitgestellten Fenster, und fügt ein vorhandenes Steuerelement.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Ein Objekt erstellt, wird eine Verbindung mit dem bereitgestellten Fenster und lädt dann ein Steuerelement.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster, ähnlich wie [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Erstellt ein Objekt, stellt eine Verbindung mit dem bereitgestellten Fenster her und lädt dann ein Steuerelement (auch Ereignissenken um eingerichtet werden können).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster, ähnlich wie [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer Ressource, und gibt das Fensterhandle.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer Ressource an.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Gibt die **IUnknown** Schnittstellenzeiger des Steuerelements in einem Fenster gehostet.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Gibt die **IUnknown** Schnittstellenzeiger, der das Hostobjekt in einem Fenster verbunden.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Initialisiert den Code zum Hosten von Steuerelementen an.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Hebt die Initialisierung des Codes zum Hosten von Steuerelementen.|  
  
 Die `HWND` Parameter in den ersten drei Funktionen müssen ein vorhandenes Fenster (fast) in einen beliebigen Typ sein. Wenn Sie jede dieser drei Funktionen explizit aufrufen (in der Regel wird nicht müssen), übergeben Sie ein Handle nicht an ein Fenster, das bereits als Host fungiert (Wenn Sie dies tun, das vorhandene Hostobjekt wird nicht freigegeben).  
  
 Die ersten sieben Funktionen aufrufen [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) implizit.  
  
> [!NOTE]
>  Die Steuerelement-hosting-API bildet die Grundlage für ATLs-Unterstützung für ActiveX-Steuerelementcontainern. Es ist jedoch in der Regel kaum Bedarf, die diese Funktionen direkt aufzurufen, wenn Sie nutzen oder ATL Wrapperklassen voll nutzen. Weitere Informationen finden Sie unter [die ATL-Klassen vereinfachen ActiveX-Steuerelementcontainern](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](which-atl-classes-facilitate-activex-control-containment-q.md)
