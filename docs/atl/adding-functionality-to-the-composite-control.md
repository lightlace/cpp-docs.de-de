---
title: "Hinzufügen von Funktionalität zu zusammengesetztes Steuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7282ba7eb80fd30175751bb5234818a5e3cf1431
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="adding-functionality-to-the-composite-control"></a>Hinzufügen von Funktionalität zu zusammengesetzten Steuerelementen
Nachdem Sie alle erforderlichen Steuerelemente in der zusammengesetzten Steuerelements eingefügt haben, besteht der nächste Schritt das Hinzufügen neuer Funktionen. Diese neue Funktionalität liegt in der Regel in zwei Kategorien unterteilt:  
  
-   Unterstützung zusätzlicher Schnittstellen und Anpassen des Verhaltens des zusammengesetzten Steuerelements mit zusätzlichen bestimmte Funktionen.  
  
-   Behandlung von Ereignissen aus enthaltenen ActiveX-Steuerelement (oder Steuerelemente) aus.  
  
 Konzentriert sich für den Zweck und der Gegenstand dieses Artikels der übrige Teil dieses Abschnitts ausschließlich auf die Behandlung von Ereignissen von ActiveX-Steuerelemente.  
  
> [!NOTE]
>  Wenn Sie Nachrichten von Windows-Steuerelemente behandeln müssen, finden Sie unter [Implementieren eines Fensters](../atl/implementing-a-window.md) für Weitere Informationen zu Meldungsbehandlung in ATL  
  
 Nach dem Einfügen eines ActiveX-Steuerelements in der Dialogfeldressource, mit der rechten Maustaste in des Steuerelements, und klicken Sie auf **Ereignishandler hinzufügen**. Wählen Sie das Ereignis zu behandeln, und klicken Sie auf **hinzufügen und Bearbeiten von**. Der Ereignishandlercode wird das Steuerelement .h-Datei hinzugefügt werden.  
  
 Verbindungspunkte für ActiveX-Steuerelemente in der zusammengesetzten Steuerelements automatisch verbunden und über Aufrufe von getrennt [:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von zusammengesetzten Steuerelementen](../atl/atl-composite-control-fundamentals.md)

