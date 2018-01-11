---
title: Bei der Kommunikation mit dem Struktursteuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ef1188c9519e57c8132a2b20fc3b272d6c0ac51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="communicating-with-a-tree-control"></a>Kommunizieren mit dem Struktursteuerelement
Sie verwenden verschiedene Methoden zum Aufrufen von Memberfunktionen einem [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Objekt je nachdem, wie das Objekt erstellt wurde:  
  
-   Wenn des Strukturansicht-Steuerelements in einem Dialogfeld befindet, verwenden Sie eine Membervariable des Typs `CTreeCtrl` , die Sie erstellen, in der Dialogfeldklasse.  
  
-   Wenn das Strukturansicht-Steuerelement ein untergeordnetes Fenster ist, verwenden die `CTreeCtrl` Objekt (oder Zeiger) verwenden, die das Objekt zu erstellen.  
  
-   Bei Verwendung einer `CTreeView` Objekt, verwenden Sie die Funktion [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) zum Abrufen eines Verweises auf die Strukturansicht-Steuerelements. Sie können mit diesem Wert eines anderen Verweises zu initialisieren oder weisen Sie die Adresse des Verweises auf eine `CTreeCtrl` Zeiger.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

