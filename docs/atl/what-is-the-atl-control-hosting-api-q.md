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
ms.openlocfilehash: 2cc85c7ca47d5d1226ffc3089e01c0755ef6c6ac
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850552"
---
# <a name="what-is-the-atl-control-hosting-api"></a>Was ist die ATL-Steuerelement-Hosting-API?
ATL des Steuerelement-hosting-API ist der Satz von Funktionen, die einem beliebigen Fenster, das als ein ActiveX-Steuerelementcontainer fungiert ermöglicht. Diese Funktionen können statisch oder dynamisch in Ihr Projekt verknüpft werden, da sie als Quellcode zur Verfügung stehen und von ATL90.dll verfügbar gemacht werden. Die Steuerelement-hosting-Funktionen sind in der folgenden Tabelle aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden, und fügt ein vorhandenes Steuerelement.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden, und lädt dann ein Steuerelement.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden und lädt dann ein Steuerelement (auch Ereignissenken um eingerichtet werden können).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer Ressource, und gibt das Fensterhandle zurück.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer Ressource an.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Gibt die `IUnknown` Schnittstellenzeiger des Steuerelements in einem Fenster gehostet.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Gibt die `IUnknown` Schnittstellenzeiger des Hostobjekts an ein Fenster verbunden.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Initialisiert den Steuerelement-hosting-Code.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Hebt die Initialisierung des Steuerelement-hosting-Codes.|  
  
 Die `HWND` Parameter in der ersten drei Funktionen müssen ein vorhandenes Fenster (nahezu) in einen beliebigen Typ sein. Wenn Sie eine dieser drei Funktionen explizit aufrufen (in der Regel müssen Sie keine), übergeben Sie ein Handle nicht an ein Fenster, das bereits als Host fungiert (Wenn Sie dies tun, das vorhandene Hostobjekt wird nicht freigegeben werden).  
  
 Rufen Sie die ersten sieben Funktionen [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) implizit.  
  
> [!NOTE]
>  Die Steuerelement-hosting-API bildet die Grundlage für ATLs-Unterstützung für ActiveX-Steuerelementcontainern. Es besteht jedoch in der Regel kaum Bedarf, diese Funktionen direkt aufzurufen, wenn Sie nutzen, oder ATLs-Wrapperklassen nutzen. Weitere Informationen finden Sie unter [der ATL-Klassen vereinfachen ActiveX-Steuerelementcontainern](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelementkapselung – häufig gestellte Fragen](which-atl-classes-facilitate-activex-control-containment-q.md)
