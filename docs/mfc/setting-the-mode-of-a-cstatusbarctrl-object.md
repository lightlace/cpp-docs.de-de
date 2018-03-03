---
title: Festlegen des CStatusBarCtrl-Objekts | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c954354321d814952ec3ac5ea148cc9177cd0fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

