---
title: Festlegen des CStatusBarCtrl-Objekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d875f2b93309e96bc3d612a8adc55b5af387026
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Festlegen des CStatusBarCtrl-Objektmodus
Es gibt zwei Modi für einen `CStatusBarCtrl` Objekt: einfache und nicht einfache. In den meisten Fällen müssen Ihre Statusleisten-Steuerelement von einem oder mehreren Teilen zusammen mit Text und vielleicht ein Symbol oder Symbole. Dies wird als nicht einfacher Modus bezeichnet. Weitere Informationen zu diesen Modus, finden Sie unter [Initialisieren der Teile eines CStatusBarCtrl-Objekts](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).  
  
 Es gibt jedoch Fälle, in denen Sie nur eine einzelne Textzeile anzeigen. In diesem Fall ist der einfache Modus für Ihre Anforderungen ausreichend. So ändern Sie den Modus der `CStatusBarCtrl` "auf" einfach Objekt, rufen Sie die [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) Memberfunktion. Sobald das StatusBar-Steuerelement im einfachen Modus befindet, legen Sie den Text durch Aufrufen der **SetText** Memberfunktion ist, übergeben 255 als Wert für die **nPane** Parameter.  
  
 Sie können die [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) Funktion, um zu bestimmen, welchen Modus der `CStatusBarCtrl` Objekt befindet sich im.  
  
> [!NOTE]
>  Wenn Statusobjekt Leiste aus einfache "auf" einfach geändert wird, oder umgekehrt, Fenster sofort neu gezeichnet wird, und ggf. werden alle definierten Segmente automatisch wiederhergestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

