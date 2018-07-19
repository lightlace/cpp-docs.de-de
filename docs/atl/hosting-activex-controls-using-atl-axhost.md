---
title: Hosten von ActiveX-Steuerelementen mit ATL-xhost | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e26fd9e80b96c2b0196e3fd0e11b9c97f0f3bff3
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027205"
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>Hosten von ActiveX-Steuerelementen mit ATL-xhost
Das Beispiel in diesem Thema zeigt AXHost erstellt und zum Hosten eines ActiveX-Steuerelements, die verschiedene ATL-Funktionen verwenden. Darüber hinaus erfahren Sie, wie die Kontrolle und die Senke Ereignisse zugreifen (mit [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) aus dem Steuerelement, das gehostet wird. Das Beispiel hostet das Kalender-Steuerelement in ein Hauptfenster oder in einem untergeordneten Fenster.  
  
 Beachten Sie, dass die Definition des Symbols USE_METHOD. Sie können den Wert dieses Symbols variiert zwischen 1 und 8 ändern. Der Wert des Symbols wird bestimmt, wie das Steuerelement erstellt wird:  
  
-   Für gerade Werte USE_METHOD, den Aufruf von der Host-Unterklassen eines Fensters erstellen und in einem Steuerelementhost konvertiert wird. Ungerade Werte erstellt der Code ein untergeordneten Fensters, das als Host fungiert.  
  
-   USE_METHOD Werte zwischen 1 und 4, den Zugriff auf das Steuerelement und das Auffangen von Ereignissen werden im Aufruf durchgeführt wird, die auch den Host erstellt. Werte zwischen 5 und 8 den Host für die Schnittstellen Abfragen und verknüpfen Sie die Senke.  
  
Hier finden Sie eine Zusammenfassung:  
  
|USE_METHOD|Host|Steuern des Zugriffs und Auffangen|Gezeigt Funktion|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|Untergeordnete Fenster|Ein Schritt|CreateControlLicEx|  
|2|Klicken Sie im Hauptfenster|Ein Schritt|AtlAxCreateControlLicEx|  
|3|Untergeordnete Fenster|Ein Schritt|CreateControlEx|  
|4|Klicken Sie im Hauptfenster|Ein Schritt|AtlAxCreateControlEx|  
|5|Untergeordnete Fenster|Mehrere Schritte|CreateControlLic|  
|6|Klicken Sie im Hauptfenster|Mehrere Schritte|AtlAxCreateControlLic|  
|7|Untergeordnete Fenster|Mehrere Schritte|CreateControl|  
|8|Klicken Sie im Hauptfenster|Mehrere Schritte|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelementkapselung – häufig gestellte Fragen](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T-Klasse](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic-Schnittstelle](../atl/reference/iaxwinhostwindowlic-interface.md)

