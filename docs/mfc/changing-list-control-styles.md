---
title: "Ändern der Stile von Listensteuerelementen | Microsoft Docs"
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
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6758cce9ab42c0dea490dd8ac9803588edceac5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-list-control-styles"></a>Ändern der Stile von Listensteuerelementen
Sie können den Fensterstil eines Steuerelements ändern ([CListCtrl](../mfc/reference/clistctrl-class.md)) zu einem beliebigen Zeitpunkt nach der Erstellung. Ändern den Fensterstil, ändern Sie die Art der Ansicht, die das Steuerelement verwendet. Z. B. zum Emulieren des Explorers möglicherweise standardimages Menüelemente und Symbolleisten-Schaltflächen für das Steuerelement zwischen verschiedenen Ansichten wechseln: Symbolansicht, Listenansicht und So weiter.  
  
 Z. B. wenn der Benutzer das Menüelement auswählt, Sie erstellen einen Aufruf von [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) das aktuelle Format des Steuerelements abzurufen, und rufen Sie anschließend [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) der Stil. Weitere Informationen finden Sie unter [Listenansicht-Steuerelemente mithilfe von](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Verfügbaren Formate sind in aufgeführt [erstellen](../mfc/reference/clistctrl-class.md#create). Die Stile `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, und `LVS_REPORT` die vier Steuerelement Listenansichten festlegen.  
  
## <a name="extended-styles"></a>Erweiterte Formate  
 Zusätzlich zu den Standardformaten für ein Listensteuerelement gibt es eine andere Gruppe, die als "Erweiterte Formate" bezeichnet. Diese Formate werden [Listenansicht-Formatvorlagen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb774732) im Windows SDK bieten eine Vielzahl von nützlichen Funktionen, die das Verhalten des Listensteuerelements anpassen. Um das Verhalten eines bestimmten Formats (z. B. Hover Auswahl) zu implementieren, stellen Sie einen Aufruf von [wird CListCtrl:: SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), übergeben das erforderliche Format. Das folgende Beispiel zeigt den Funktionsaufruf:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  Zur Auswahl der Hover arbeiten, zudem müssen Sie entweder **Wenn zusätzlich LVS_EX_ONECLICKACTIVATE** oder **LVS_EX_TWOCLICKACTIVATE gesetzt** eingeschaltet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

