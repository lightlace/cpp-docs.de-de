---
title: Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts | Microsoft-Dokumentation
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
ms.openlocfilehash: 3c68603eff0393d76af4e0617548e5bf1dd4aa63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413684"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts

Hier ist ein Beispiel für eine typische Verwendung des [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):

### <a name="to-use-a-status-bar-control-with-parts"></a>Verwenden Sie ein Statusleisten-Steuerelement mit Teilen

1. Erstellen der `CStatusBarCtrl` Objekt.

1. Rufen Sie [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) , wenn Sie die minimale Höhe des das StatusBar-Steuerelement festlegen möchten den Zeichenbereich.

1. Rufen Sie [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) die Hintergrundfarbe des das StatusBar-Steuerelement festlegen.

1. Rufen Sie [Sie SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) So legen Sie die Anzahl der Teile in einer Statusleisten-Steuerelement und die Koordinate des rechten Rands der einzelnen Teile fest.

1. Rufen Sie [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) den Text in einem bestimmten Teil des das StatusBar-Steuerelement festlegen. Die Nachricht wird den Teil des Steuerelements, das geändert wurde, aufgrund dessen der neue Text angezeigt, wenn das Steuerelement als Nächstes die WM_PAINT-Meldung erhält, ungültig.

In einigen Fällen muss die Statusleiste nur eine Textzeile angezeigt. In diesem Fall stellen einen Aufruf von [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Dadurch wird das StatusBar-Steuerelement, in "einfach" versetzt, die eine einzelne Textzeile anzeigt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

