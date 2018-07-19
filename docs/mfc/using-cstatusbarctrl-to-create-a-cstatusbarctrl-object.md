---
title: Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts | Microsoft Docs
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
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb378bba1505f8bbc3739c070d52abe9ef4f8afc
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953824"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts
Hier ist ein Beispiel für eine typische Verwendung des [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### <a name="to-use-a-status-bar-control-with-parts"></a>Verwenden Sie ein Statusleisten-Steuerelement mit Teilen  
  
1.  Erstellen der `CStatusBarCtrl` Objekt.  
  
2.  Rufen Sie [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) , wenn Sie die Mindesthöhe eines Statusleisten-Steuerelement festlegen möchten die Zeichenfläche.  
  
3.  Rufen Sie [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) zum Festlegen der Hintergrundfarbe für das StatusBar-Steuerelement.  
  
4.  Rufen Sie [Sie SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) So legen Sie die Anzahl der Teile in einer Statusleisten-Steuerelement und dem rechten Rand der einzelnen Teile der Koordinate fest.  
  
5.  Rufen Sie [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) auf den Text in einem bestimmten Teil des Statusleisten-Steuerelement festlegen. Die Meldung erklärt den Teil des Steuerelements, das geändert wurde, aufgrund dessen der neue Text angezeigt, wenn das Steuerelement als Nächstes WM_PAINT-Meldung empfängt.  
  
 In einigen Fällen muss die Statusleiste nur eine Textzeile angezeigt. In diesem Fall stellen einen Aufruf von [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Mit dieser Option wird das StatusBar-Steuerelement in den "einfache" versetzt, das eine einzelne Textzeile anzeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

