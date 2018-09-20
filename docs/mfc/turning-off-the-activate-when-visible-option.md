---
title: Durch das Deaktivieren der Option "aktiviert wenn sichtbar" | Microsoft-Dokumentation
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
ms.openlocfilehash: 7cb585496e6acf1c0ad94a43500e6d9a4830a2ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381282"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Deaktivieren der Option „Aktiviert, wenn sichtbar“

Ein Steuerelement verfügt über zwei grundlegende Zustände: aktiv und inaktiv. In der Vergangenheit unterschieden sich diese Zustände dadurch, ob das Steuerelement ein Fenster hatte oder nicht. Ein aktives Steuerelement wies ein Fenster auf, ein inaktives Steuerelement wies kein Fenster auf. Mit der Einführung der fensterlose Aktivierung, ist diese Unterscheidung nicht mehr universell, gilt aber weiterhin für viele Steuerelemente.

Im Vergleich mit dem Rest der Initialisierung von ActiveX-Steuerelement üblicherweise ausgeführt werden, ist die Erstellung eines Fensters ein sehr aufwändiger Vorgang. Im Idealfall würde ein Steuerelement verzögern, erstellen das Fenster, bis Sie absolut notwendig.

Viele Steuerelemente müssen nicht die gesamte Zeit aktiv zu werden, die sie in einem Container angezeigt werden. Häufig kann ein Steuerelement in den inaktiven Status bleiben, bis der Benutzer einen Vorgang, der es aktiv ist (z. B. ausführt, klicken mit der Maus oder durch Drücken der TAB-Taste) wird benötigt. Damit ein Steuerelement auf inaktiv bleiben, bis der Container aktiviert werden muss, entfernen Sie die **OLEMISC_ACTIVATEWHENVISIBLE** Flag aus der Steuerelementflags:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

Die **OLEMISC_ACTIVATEWHENVISIBLE** Flag automatisch ausgelassen wird, wenn Sie deaktivieren die **aktivieren, wenn sichtbar** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) auf der Seite die MFC-ActiveX- Steuerelement-Assistent bei der Erstellung des Steuerelements.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

