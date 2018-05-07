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
ms.openlocfilehash: 4b61fb9450e6206c8f96102b5feeec6fbf3bead3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="settings-for-the-tool-tip-control"></a>Einstellungen für das QuickInfo-Steuerelement
Sie können das QuickInfo-Steuerelement ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) entweder als aktiv oder als inaktiv festlegen. Wenn Sie es als aktiv festlegen, wird das QuickInfo-Steuerelement angezeigt, wenn Sie den Cursor auf einem Tool platzieren. Wenn Sie es als inaktiv festlegen, wird das QuickInfo-Steuerelement auch dann nicht angezeigt, wenn sich der Cursor auf einem Tool befindet. Rufen Sie [Activate](../mfc/reference/ctooltipctrl-class.md#activate) auf, um ein QuickInfo-Steuerelement zu aktivieren oder deaktivieren.  
  
 Sie können die Anzeige eines aktiven QuickInfo-Steuerelements, wenn sich der Cursor auf einem Tool befindet, mithilfe der Formatvorlage **TTS_ALWAYSTIP** so festlegen, dass die Anzeige unabhängig vom Aktivierungszustand des besitzenden Fensters erfolgt. Wenn Sie dieses Formatvorlage nicht verwenden, wird das QuickInfo-Steuerelement angezeigt, wenn das besitzende Fenster des Steuerelements aktiv ist, aber nicht, wenn es nicht aktiv ist.  
  
 Die meisten Anwendungen enthalten Symbolleisten mit Tools, die Menübefehlen entsprechen. Für solche Tools ist es sinnvoll, wenn im QuickInfo-Steuerelement der gleiche Text wie im entsprechenden Menüelement angezeigt wird. Das System entfernt automatisch das kaufmännische und-Zeichen (&) Accelerator Zeichen aus allen Zeichenfolgen, die an ein QuickInfo-Steuerelement, übergeben, es sei denn, das Steuerelement hat den **TTS_NOPREFIX** Stil.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

