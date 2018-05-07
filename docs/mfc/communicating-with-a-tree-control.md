---
title: Bei der Kommunikation mit dem Struktursteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af0b248d5e32b535c23cc17b48efdd551dad7a2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="communicating-with-a-tree-control"></a>Kommunizieren mit dem Struktursteuerelement
Sie verwenden verschiedene Methoden zum Aufrufen von Memberfunktionen einem [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Objekt je nachdem, wie das Objekt erstellt wurde:  
  
-   Wenn des Strukturansicht-Steuerelements in einem Dialogfeld befindet, verwenden Sie eine Membervariable des Typs `CTreeCtrl` , die Sie erstellen, in der Dialogfeldklasse.  
  
-   Wenn das Strukturansicht-Steuerelement ein untergeordnetes Fenster ist, verwenden die `CTreeCtrl` Objekt (oder Zeiger) verwenden, die das Objekt zu erstellen.  
  
-   Bei Verwendung einer `CTreeView` Objekt, verwenden Sie die Funktion [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) zum Abrufen eines Verweises auf die Strukturansicht-Steuerelements. Sie können mit diesem Wert eines anderen Verweises zu initialisieren oder weisen Sie die Adresse des Verweises auf eine `CTreeCtrl` Zeiger.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

