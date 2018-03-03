---
title: Hosting von ActiveX-Steuerelementen mit ATL AXHost | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2aac8a8b9cbf0b72378a286943faa6e36a8f3f74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>Hosting von ActiveX-Steuerelementen mit ATL AXHost
Im Beispiel in diesem Thema wird gezeigt, wie AXHost erstellt und wie mit verschiedenen Funktionen von ATL-ActiveX-Steuerelement gehostet. Außerdem wird gezeigt, wie auf das Steuerelement und die Senke Ereignisse zugreifen (mit [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) aus dem Steuerelement, das gehostet wird. Im Beispiel hostet das Kalender-Steuerelement in ein Hauptfenster oder ein untergeordnetes Fenster.  
  
 Beachten Sie die Definition der `USE_METHOD` Symbol. Sie können den Wert dieses Symbols variiert zwischen 1 und 8 ändern. Der Wert des Symbols wird bestimmt, wie das Steuerelement erstellt wird:  
  
-   Für Werte des gerader `USE_METHOD`, den Aufruf beim Erstellen von der Host-Unterklassen eines Fensters und konvertiert sie in einem Steuerelementhost. Für die ungeraden Werte erstellt der Code ein untergeordnetes Fenster, das als Host fungiert.  
  
-   Für Werte des `USE_METHOD` zwischen 1 und 4, der Zugriff auf das Steuerelement und Auffangen von Ereignissen von aktivitätsdesignerattribute im Aufruf, die auch auf den Host erstellt. Werte zwischen 5 und 8 Fragen Sie den Host für die Schnittstellen und die Senke zu verknüpfen.  
  
 Hier finden Sie eine Zusammenfassung:  
  
|USE_METHOD|Host|Steuern des Zugriffs und Auffangen|Funktion veranschaulicht|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|Untergeordnete Fenster|Ein Schritt|CreateControlLicEx|  
|2|Im Hauptfenster|Ein Schritt|AtlAxCreateControlLicEx|  
|3|Untergeordnete Fenster|Ein Schritt|CreateControlEx|  
|4|Im Hauptfenster|Ein Schritt|AtlAxCreateControlEx|  
|5|Untergeordnete Fenster|Mehrere Schritte|CreateControlLic|  
|6|Im Hauptfenster|Mehrere Schritte|AtlAxCreateControlLic|  
|7|Untergeordnete Fenster|Mehrere Schritte|CreateControl|  
|8|Im Hauptfenster|Mehrere Schritte|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Zur steuerelementkapselung](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T-Klasse](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic-Schnittstelle](../atl/reference/iaxwinhostwindowlic-interface.md)

