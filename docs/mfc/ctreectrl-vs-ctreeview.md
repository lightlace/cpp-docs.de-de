---
title: CTreeCtrl-im Vergleich zu CTreeView | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb0c1b7a7bf73ab70bbccca6f2a9ccc2ab385516
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl-im Vergleich zu CTreeView
MFC enthält zwei Klassen, die von Tree-Steuerelementen gekapselt: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) und [CTreeView](../mfc/reference/ctreeview-class.md). Jede Klasse ist in anderen Situationen nützlich.  
  
 Verwendung `CTreeCtrl` Wenn Sie ein einfaches untergeordnetes Fenstersteuerelement benötigen, z. B. in einem Dialogfeld. Insbesondere verwenden sollten `CTreeCtrl` bei weiteren untergeordneten Steuerelemente im Fenster, wie Sie in das Dialogfeld dar.  
  
 Verwendung `CTreeView` sollen des Strukturansicht-Steuerelements, zu einem Ansichtsfenster in Dokument-/Ansichtarchitektur fungieren sowie ein Strukturansicht-Steuerelement. Ein `CTreeView` wird der gesamte Clientbereich eines Rahmenfensters oder unterteiltes Fenster einnehmen. Es wird automatisch angepasst werden, wenn das übergeordnete Fenster geändert wird, und von Menüs, Zugriffstasten und Symbolleisten Command-Meldungen verarbeitet werden können. Da ein Strukturansicht-Steuerelement zum Anzeigen der Struktur erforderlichen Daten enthält, die entsprechenden Document-Objekt muss nicht in sich als kompliziert erweisen – Sie können auch [CDocument](../mfc/reference/cdocument-class.md) als den Dokumenttyp in Ihr Dokumentvorlage.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

