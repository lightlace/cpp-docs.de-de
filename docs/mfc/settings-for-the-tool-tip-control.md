---
title: "Einstellungen für das QuickInfo-Steuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 406e35b6ab694ca972d4cd6add0dcca7586e5005
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-tool-tip-control"></a>Einstellungen für das QuickInfo-Steuerelement
Sie können das QuickInfo-Steuerelement ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) entweder als aktiv oder als inaktiv festlegen. Wenn Sie es als aktiv festlegen, wird das QuickInfo-Steuerelement angezeigt, wenn Sie den Cursor auf einem Tool platzieren. Wenn Sie es als inaktiv festlegen, wird das QuickInfo-Steuerelement auch dann nicht angezeigt, wenn sich der Cursor auf einem Tool befindet. Rufen Sie [Activate](../mfc/reference/ctooltipctrl-class.md#activate) auf, um ein QuickInfo-Steuerelement zu aktivieren oder deaktivieren.  
  
 Sie können die Anzeige eines aktiven QuickInfo-Steuerelements, wenn sich der Cursor auf einem Tool befindet, mithilfe der Formatvorlage **TTS_ALWAYSTIP** so festlegen, dass die Anzeige unabhängig vom Aktivierungszustand des besitzenden Fensters erfolgt. Wenn Sie dieses Formatvorlage nicht verwenden, wird das QuickInfo-Steuerelement angezeigt, wenn das besitzende Fenster des Steuerelements aktiv ist, aber nicht, wenn es nicht aktiv ist.  
  
 Die meisten Anwendungen enthalten Symbolleisten mit Tools, die Menübefehlen entsprechen. Für solche Tools ist es sinnvoll, wenn im QuickInfo-Steuerelement der gleiche Text wie im entsprechenden Menüelement angezeigt wird. Das System entfernt automatisch das kaufmännische und-Zeichen (&) Accelerator Zeichen aus allen Zeichenfolgen, die an ein QuickInfo-Steuerelement, übergeben, es sei denn, das Steuerelement hat den **TTS_NOPREFIX** Stil.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

