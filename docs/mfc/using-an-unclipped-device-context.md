---
title: Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung | Microsoft Docs
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
ms.openlocfilehash: 6d4fcfbe8e8e7eb174f85ced03bec822b4968bde
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954334"
---
# <a name="using-an-unclipped-device-context"></a>Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung
Wenn Sie absolut sicher sind, dass das Steuerelement nicht außerhalb des Clientrechtecks gezeichnet wird, können Sie ein kleines, aber erkennbare Geschwindigkeitszuwachs umsetzen können durch das Deaktivieren des Aufrufs von `IntersectClipRect` , erfolgt durch `COleControl`. Entfernen Sie zu diesem Zweck die *ClipPaintDC* Flag aus der Gruppe von Flags, die zurückgegebene [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 Der Code zum Entfernen dieses Flag wird automatisch generiert, wenn Sie die Option der **Gerätekontexts ohne Gerätekontext** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite, wenn das Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellen.  
  
 Wenn Sie fensterlosen Aktivierung verwenden, ist diese Optimierung wirkungslos.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

