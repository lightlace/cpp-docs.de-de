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
ms.openlocfilehash: 8c76dc44993615e17ea3d99f9ac018a748e24d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-an-unclipped-device-context"></a>Verwenden eines Gerätekontexts ohne Clippingbereichsanpassung
Wenn Sie absolut sicher sind, dass das Steuerelement nicht außerhalb des Clientrechtecks gezeichnet wird, können Sie ein kleines, aber erkennbare Geschwindigkeitszuwachs umsetzen können durch das Deaktivieren des Aufrufs von `IntersectClipRect` , erfolgt durch `COleControl`. Entfernen Sie zu diesem Zweck die **ClipPaintDC** Flag aus der Gruppe von Flags, die zurückgegebene [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]  
  
 Der Code zum Entfernen dieses Flag wird automatisch generiert, wenn Sie die Option der **Gerätekontexts ohne Gerätekontext** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite, wenn das Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellen.  
  
 Wenn Sie fensterlosen Aktivierung verwenden, ist diese Optimierung wirkungslos.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

