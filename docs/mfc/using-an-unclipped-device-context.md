---
title: Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 222a3fb60d07176b1ba8e586e142865164bc215f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596511"
---
# <a name="using-an-unclipped-device-context"></a>Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung

Wenn Sie nicht absolut sicher sind, dass das Steuerelement nicht außerhalb des Clientrechtecks zeichnet, profitieren Sie von eine Geschwindigkeit erzielt durch das Deaktivieren des Aufrufs von `IntersectClipRect` , erfolgt durch `COleControl`. Entfernen Sie zu diesem Zweck die *ClipPaintDC* Flag aus dem Satz von Flags, die vom [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

Der Code So entfernen Sie dieses Flag wird automatisch generiert, wenn Sie die Option der **Ungeschnittener Gerätekontext** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite, wenn das Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellen.

Wenn Sie fensterlosen Aktivierung verwenden, ist diese Optimierung wirkungslos.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

