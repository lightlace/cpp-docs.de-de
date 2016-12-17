---
title: "Hosting ActiveX Controls Using ATL AXHost"
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
  - "ActiveX-Steuerelemente [C++], Hosting"
  - "AXHost method"
  - "Calendar control (ActiveX)"
  - "Calendar control (ActiveX), hosting with ATL AXHost"
  - "CAxWindow2T class"
  - "Hosting von ActiveX-Steuerelementen"
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hosting ActiveX Controls Using ATL AXHost
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Beispiel in diesem Thema wird gezeigt, wie AXHost erstellt und wie ein ActiveX\-Steuerelement mithilfe verschiedener ATL\-Funktionen hostet.  Es zeigt auch, wie auf das Steuerelement zugegriffen wird und Ereignisse \(mithilfe [IDispEventImpl](../atl/reference/idispeventimpl-class.md)\) vom Steuerelement sinkt, das gehostet wird.  Das Beispiel hostet das Kalendersteuerelement in einem Hauptfenster oder in einem untergeordneten Fenster.  
  
 Beachten Sie die Definition des Symbols `USE_METHOD`.  Sie können den Wert dieses Symbols ändern, um zwischen 1 und 8. variiert.  Der Wert des Symbols bestimmt, wie das Steuerelement erstellt wird:  
  
-   Für nur Werte von `USE_METHOD`, ordnet der aufrufen, um des Hosts erstellen ein Fenster unter und konvertiert sie in einem Steuerhost.  Für ungerade Werte erstellt der Code ein untergeordnetes Fenster, das als Host fungiert.  
  
-   Für Werte von `USE_METHOD` zwischen 1 und 4, werden Zugriff auf das Steuerelement und das Verringern von Ereignissen im Aufruf erreicht, der auch den Host erstellt.  Werte zwischen 5 und 8 fragen den Host für Schnittstellen ab und verknüpfen die Senke.  
  
 Es folgt eine Zusammenfassung:  
  
|USE\_METHOD|Host|Zugriff und Ereignissinken|Funktion veranschaulicht|  
|-----------------|----------|--------------------------------|------------------------------|  
|1|Untergeordnete Fenster|Ein Schritt|CreateControlLicEx|  
|2|Hauptfenster|Ein Schritt|AtlAxCreateControlLicEx|  
|3|Untergeordnete Fenster|Ein Schritt|CreateControlEx|  
|4|Hauptfenster|Ein Schritt|AtlAxCreateControlEx|  
|5|Untergeordnete Fenster|Mehrere Schritte|CreateControlLic|  
|6|Hauptfenster|Mehrere Schritte|AtlAxCreateControlLic|  
|7|Untergeordnete Fenster|Mehrere Schritte|CreateControl|  
|8|Hauptfenster|Mehrere Schritte|AtlAxCreateControl|  
  
 [!CODE [NVC_ATL_AxHost#1](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_AxHost#1)]  
  
## Siehe auch  
 [Fragen und Antworten zur Steuerelementkapselung](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](../Topic/AtlAxCreateControl.md)   
 [AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)   
 [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)   
 [AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)   
 [CAxWindow2T Class](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Interface](../atl/reference/iaxwinhostwindowlic-interface.md)