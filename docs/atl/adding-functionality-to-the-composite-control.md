---
title: "Adding Functionality to the Composite Control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Ereignisse"
  - "Zusammengesetzte Steuerelemente, Ereignisbehandlung"
  - "event handlers [C++], ActiveX-Steuerelemente"
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Adding Functionality to the Composite Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie alle erforderlichen Steuerelemente in das zusammengesetzte Steuerelement eingefügt haben, besteht der nächste Schritt mit ein, neue Funktionen hinzuzufügen.  Diese neuen Funktionen gehören normalerweise zwei Kategorien:  
  
-   Zusätzliche Schnittstellen und Anpassen des Verhaltens des zusammengesetzten Steuerelements mit weiteren, bestimmte Funktionen unterstützen.  
  
-   Das Behandeln vom übergeordneten ActiveX\-Steuerelement \(oder von Steuerelementen\).  
  
 Für und für den Gültigkeitsbereich dieses Artikels, konzentriert sich der Rest dieses Abschnitts nur auf Ereignisbehandlung von ActiveX\-Steuerelementen.  
  
> [!NOTE]
>  Wenn Sie Meldungen von den Windows\-Steuerelementen bearbeiten müssen, finden Sie weitere Informationen zu [Implementieren eines Fensters](../atl/implementing-a-window.md) Meldungsbehandlung in ATL.  
  
 Nachdem Sie ein ActiveX\-Steuerelement in der Dialogfeldressource eingefügt haben, klicken Sie mit der rechten Maustaste auf das Steuerelement und klicken Sie auf **Ereignishandler hinzufügen**.  Wählen Sie das Ereignis aus, das Sie auf **Hinzufügen und bearbeiten** behandeln und auf.  Der Ereignishandler wird der H\-Datei des Steuerelements hinzugefügt.  
  
 Verbindungspunkte für ActiveX\-Steuerelemente im zusammengesetzten Steuerelement werden automatisch über Aufrufe [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md) verbunden und getrennt.  
  
## Siehe auch  
 [Grundlagen von zusammengesetzten Steuerelementen](../atl/atl-composite-control-fundamentals.md)