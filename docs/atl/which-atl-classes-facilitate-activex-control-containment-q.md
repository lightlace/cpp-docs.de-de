---
title: Die ATL-Klassen zu ActiveX-Steuerelementcontainern vereinfachen? | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 880c7bd52476614a4356690aff2fda286e9f3aef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="which-atl-classes-facilitate-activex-control-containment"></a>Die ATL-Klassen zu ActiveX-Steuerelementcontainern vereinfachen?
Hosten von Steuerelementen von ATL-Code erfordern nicht Ihnen die Verwendung von ATL-Klassen; Sie können einfach erstellen eine **"AtlAxWin80"** Fenster und verwenden Sie die Steuerelement-hosting-API bei Bedarf (Weitere Informationen finden Sie unter **was ATL-Steuerelement-Hosting-API ist**. Allerdings erleichtern die folgenden Klassen die Containment-Funktionen zu verwenden.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Umschließt ein **"AtlAxWin80"** Fenster Methoden für das Erstellen des Fensters, Erstellen eines Steuerelements und/oder ein Steuerelement anfügen, um das Fenster und Abrufen von Schnittstellenzeigern auf das Hostobjekt bereitstellt.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Umschließt ein **"AtlAxWinLic80"** Fenster für das Erstellen des Fensters, Erstellen eines Steuerelements und/oder ein lizenziertes Steuerelement an die Fenster angefügt und Abrufen von Schnittstellenzeigern auf das Hostobjekt, das Methoden bereitstellt.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Fungiert als Basisklasse für ActiveX-Steuerelementklassen basierend auf einer Ressource. Solche Steuerelemente können andere ActiveX-Steuerelemente enthalten.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Fungiert als Basisklasse für Klassen basierend auf einer Ressource. Solche Dialogfelder können ActiveX-Steuerelemente enthalten.|  
|[CWindow](../atl/reference/cwindow-class.md)|Stellt eine Methode [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), als Rückgabe erhalten Sie einen Schnittstellenzeiger auf ein Steuerelement, das die entsprechende Hostfenster-ID angegeben. Darüber hinaus die Windows-API-Wrapper verfügbar gemacht, indem `CWindow` im Allgemeinen fensterverwaltung vereinfachen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)

