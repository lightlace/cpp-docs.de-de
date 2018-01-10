---
title: Durch das Deaktivieren der Option "aktiviert wenn sichtbar" | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25521d75921b377730a7f9afac71f2a60c055216
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="turning-off-the-activate-when-visible-option"></a>Deaktivieren der Option „Aktiviert, wenn sichtbar“
Ein Steuerelement verfügt über zwei grundlegende Zustände: aktiv und inaktiv. In der Vergangenheit unterschieden sich diese Zustände dadurch, ob das Steuerelement ein Fenster hatte oder nicht. Ein aktives Steuerelement wies ein Fenster auf, ein inaktives Steuerelement wies kein Fenster auf. Mit der Einführung der fensterlose Aktivierung, ist diese Unterscheidung nicht mehr universell, gilt aber weiterhin für viele Steuerelemente.  
  
 Im Vergleich mit dem Rest der Initialisierung von ActiveX-Steuerelement in der Regel ausgeführt, ist die Erstellung eines Fensters ein sehr aufwendiger Vorgang. Im Idealfall würden ein Steuerelement aufschieben, erstellen das Fenster, bis dies absolut notwendig.  
  
 Viele Steuerelemente müssen nicht die gesamte Zeit aktiv zu sein, die sie in einem Container angezeigt werden. Häufig kann ein Steuerelement in den inaktiven Zustand verbleiben, bis der Benutzer einen Vorgang, der benötigt wird ausführt, um (z. B. durch Klicken mit der Maus oder drücken Sie die TAB-Taste) aktiviert werden. Um bewirken, dass ein Steuerelement inaktiv bleiben, bis der Container aktiviert werden muss, entfernen Sie die **OLEMISC_ACTIVATEWHENVISIBLE** Flag aus verschiedene Steuerungsflags:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 Die **OLEMISC_ACTIVATEWHENVISIBLE** Flag wird automatisch weggelassen werden, wenn Sie deaktivieren die **aktivieren, wenn sichtbar** -Option in der [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite des MFC-ActiveX- Steuerelement-Assistent bei der Erstellung des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

