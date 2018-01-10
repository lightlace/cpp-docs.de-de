---
title: "Zerstören des Listensteuerelements | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdaafb8a6951050dac0022e0e6e8874b48d688e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-list-control"></a>Zerstören des Listensteuerelements
Wenn Sie einbetten Ihre [CListCtrl](../mfc/reference/clistctrl-class.md) als Datenmember einer Klasse Ansichts- oder Dialogfeldobjekt-Objekt zerstört wird, wenn der Besitzer zerstört wird. Bei Verwendung einer [CListView](../mfc/reference/clistview-class.md), das Framework zerstört das Steuerelement aus, wenn sie die Ansicht zerstört.  
  
 Wenn Sie für Ihre Liste Daten in das Strukturelement-Steuerelement, statt die Anwendung zu speichernde anordnen möchten, müssen Sie für die Aufhebung der Zuordnung anordnen. Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Darüber hinaus sind Sie verantwortlich für das Freigeben von jeder Bilderliste für das, die Sie erstellt und dem Listensteuerelement-Objekt zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

