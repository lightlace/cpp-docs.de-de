---
title: Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2143ea37cfe9448e43aacfa75622beab93d2fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382333"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Verwenden von CToolTipCtrl zum Erstellen und Bearbeiten eines CToolTipCtrl-Objekts
Hier ist ein Beispiel der [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) Verwendung:  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Zum Erstellen und Bearbeiten von CToolTipCtrl  
  
1.  Erstellen der `CToolTipCtrl` Objekt.  
  
2.  Rufen Sie [erstellen](../mfc/reference/ctooltipctrl-class.md#create) erstellen die allgemeine Windows-Tool QuickInfo-Steuerelement und fügen Sie es auf die `CToolTipCtrl` Objekt.  
  
3.  Rufen Sie [Sie AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) ein Tool mit der ToolTip-Steuerelements zu registrieren, damit die Informationen gespeichert, die in der QuickInfo angezeigt wird, wenn der Cursor in das Tool befindet.  
  
4.  Rufen Sie [Sie SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) die Informationen festgelegt, der eine QuickInfo für ein Tool verwaltet.  
  
5.  Rufen Sie [Sie SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) , legen Sie einen neuen umschließenden Rechtecks für ein Tool.  
  
6.  Rufen Sie [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) zum Testen eines Punkt, um zu bestimmen, ob es sich innerhalb des umschließenden Rechtecks des angegebenen Tools ist, und wenn dies der Fall ist, Abrufen von Informationen zu diesem Tool.  
  
7.  Rufen Sie [Sie GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) zum Abrufen der Anzahl der Tools registriert das QuickInfo-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

