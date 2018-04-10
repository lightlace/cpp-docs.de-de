---
title: Bereitstellen flimmerfreier Aktivierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f14998ce663e5a8e53901acf9192719fa41e724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="providing-flicker-free-activation"></a>Bereitstellen flimmerfreier Aktivierung
Wenn das Steuerelement sich selbst in die inaktiven und den aktiven Status identisch zeichnet (und nicht fensterlosen Aktivierung verwendet), können Sie vermeiden die Zeichenoperationen und die begleitende visual Flimmern, die normalerweise vorkommen, wenn Sie den Übergang zwischen den inaktiven vornehmen und aktiv. Um dies zu erreichen, fügen die **NoFlickerActivate** -Flag in der Gruppe von Flags, die zurückgegebene [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 Der Code auf dieses Flag einschließen, wird automatisch generiert, wenn Sie die Option der **flimmerfreier Aktivierung** option die [Steuerelementeinstellungen](../mfc/reference/control-settings-mfc-activex-control-wizard.md) Seite zum Erstellen des Steuerelements mit MFC-ActiveX-Steuerelement-Assistenten.  
  
 Wenn Sie fensterlosen Aktivierung verwenden, ist diese Optimierung wirkungslos.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)

