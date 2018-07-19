---
title: Einstellungen für das QuickInfo-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39de60d17dae5a6d7b2965350162117d049c29c8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951113"
---
# <a name="settings-for-the-tool-tip-control"></a>Einstellungen für das QuickInfo-Steuerelement
Sie können das QuickInfo-Steuerelement ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) entweder als aktiv oder als inaktiv festlegen. Wenn Sie es als aktiv festlegen, wird das QuickInfo-Steuerelement angezeigt, wenn Sie den Cursor auf einem Tool platzieren. Wenn Sie es als inaktiv festlegen, wird das QuickInfo-Steuerelement auch dann nicht angezeigt, wenn sich der Cursor auf einem Tool befindet. Rufen Sie [Activate](../mfc/reference/ctooltipctrl-class.md#activate) auf, um ein QuickInfo-Steuerelement zu aktivieren oder deaktivieren.  
  
 Sie können festlegen, dass eine aktive QuickInfo, die QuickInfo angezeigt, wenn der Cursor auf einem Tool befindet, und zwar unabhängig davon, ob Besitzerfenster des QuickInfo-Steuerelements aktiv oder inaktiv ist, wird mithilfe des TTS_ALWAYSTIP-Stils. Wenn Sie dieses Formatvorlage nicht verwenden, wird das QuickInfo-Steuerelement angezeigt, wenn das besitzende Fenster des Steuerelements aktiv ist, aber nicht, wenn es nicht aktiv ist.  
  
 Die meisten Anwendungen enthalten Symbolleisten mit Tools, die Menübefehlen entsprechen. Für solche Tools ist es sinnvoll, wenn im QuickInfo-Steuerelement der gleiche Text wie im entsprechenden Menüelement angezeigt wird. Das System entfernt automatisch das kaufmännische und-Zeichen (&) Accelerator Zeichen aus allen Zeichenfolgen, ein QuickInfo-Steuerelement, das an, wenn das Steuerelement das TTS_NOPREFIX-Format hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

