---
title: "Zerst&#246;ren des Listensteuerelements"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl-Klasse, Entfernen von Steuerelementen"
  - "List-Steuerelemente, Zerstören"
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zerst&#246;ren des Listensteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie das [Verwendung](../mfc/reference/clistctrl-class.md)\-Objekt als Datenmember einer Ansicht oder der Dialogfeldklasse einbetten, wird sie zerstört, wenn sein Besitzer zerstört wird.  Wenn Sie [CListView](../mfc/reference/clistview-class.md) verwenden, zerstört das Framework das Steuerelement, wenn die Ansicht gelöscht.  
  
 Wenn Sie für einige der in der Anwendung angeordnet anstatt das Listensteuerelement zu speichernden Listendaten, müssen Sie für die Freigabe anordnen.  Weitere Informationen finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Rückruf\-Elemente und die Rückruf\-Maske](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
 Außerdem können Sie für die Freigabe aller Bildlisten zuständig, die dem Listensteuerelementobjekt erstellt und belegen.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)