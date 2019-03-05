---
title: Deaktivieren der Option „Aktiviert, wenn sichtbar“
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: a7afe9617aa356916fe184828d7684f228293e39
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304729"
---
# <a name="turning-off-the-activate-when-visible-option"></a>Deaktivieren der Option „Aktiviert, wenn sichtbar“

Ein Steuerelement verfügt über zwei grundlegende Zustände: aktiv und inaktiv. In der Vergangenheit unterschieden sich diese Zustände dadurch, ob das Steuerelement ein Fenster hatte oder nicht. Ein aktives Steuerelement wies ein Fenster auf, ein inaktives Steuerelement wies kein Fenster auf. Mit der Einführung der fensterlose Aktivierung, ist diese Unterscheidung nicht mehr universell, gilt aber weiterhin für viele Steuerelemente.

Im Vergleich mit dem Rest der Initialisierung von ActiveX-Steuerelement üblicherweise ausgeführt werden, ist die Erstellung eines Fensters ein sehr aufwändiger Vorgang. Im Idealfall würde ein Steuerelement verzögern, erstellen das Fenster, bis Sie absolut notwendig.

Viele Steuerelemente müssen nicht die gesamte Zeit aktiv zu werden, die sie in einem Container angezeigt werden. Häufig kann ein Steuerelement in den inaktiven Status bleiben, bis der Benutzer einen Vorgang, der es aktiv ist (z. B. ausführt, klicken mit der Maus oder durch Drücken der TAB-Taste) wird benötigt. Damit ein Steuerelement auf inaktiv bleiben, bis der Container aktiviert werden muss, entfernen Sie die **OLEMISC_ACTIVATEWHENVISIBLE** Flag aus der Steuerelementflags:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

Die **OLEMISC_ACTIVATEWHENVISIBLE** Flag automatisch ausgelassen wird, wenn Sie deaktivieren die **aktivieren, wenn sichtbar** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) auf der Seite die MFC-ActiveX- Steuerelement-Assistent bei der Erstellung des Steuerelements.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)
