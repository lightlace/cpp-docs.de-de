---
title: Durch das Deaktivieren der Option "aktiviert wenn sichtbar" | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5625e7d05ea09188aaa2ea50ca629204a4bacc07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="turning-off-the-activate-when-visible-option"></a>Deaktivieren der Option „Aktiviert, wenn sichtbar“
Ein Steuerelement verfügt über zwei grundlegende Zustände: aktiv und inaktiv. In der Vergangenheit unterschieden sich diese Zustände dadurch, ob das Steuerelement ein Fenster hatte oder nicht. Ein aktives Steuerelement wies ein Fenster auf, ein inaktives Steuerelement wies kein Fenster auf. Mit der Einführung der fensterlose Aktivierung, ist diese Unterscheidung nicht mehr universell, gilt aber weiterhin für viele Steuerelemente.  
  
 Im Vergleich mit dem Rest der Initialisierung von ActiveX-Steuerelement in der Regel ausgeführt, ist die Erstellung eines Fensters ein sehr aufwendiger Vorgang. Im Idealfall würden ein Steuerelement aufschieben, erstellen das Fenster, bis dies absolut notwendig.  
  
 Viele Steuerelemente müssen nicht die gesamte Zeit aktiv zu sein, die sie in einem Container angezeigt werden. Häufig kann ein Steuerelement in den inaktiven Zustand verbleiben, bis der Benutzer einen Vorgang, der benötigt wird ausführt, um (z. B. durch Klicken mit der Maus oder drücken Sie die TAB-Taste) aktiviert werden. Um bewirken, dass ein Steuerelement inaktiv bleiben, bis der Container aktiviert werden muss, entfernen Sie die **OLEMISC_ACTIVATEWHENVISIBLE** Flag aus verschiedene Steuerungsflags:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 Die **OLEMISC_ACTIVATEWHENVISIBLE** Flag wird automatisch weggelassen werden, wenn Sie deaktivieren die **aktivieren, wenn sichtbar** -Option in der [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite des MFC-ActiveX- Steuerelement-Assistent bei der Erstellung des Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

