---
title: Verwenden einer Clippingbereichsanpassung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 479009865fe9fd226466059382456f403e90c18a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389589"
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

