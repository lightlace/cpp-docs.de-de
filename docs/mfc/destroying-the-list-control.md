---
title: Zerstören des Listensteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edb26671ba775cfa7daf98d39c7eccc9fd4111bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343281"
---
# <a name="destroying-the-list-control"></a>Zerstören des Listensteuerelements
Wenn Sie einbetten Ihre [CListCtrl](../mfc/reference/clistctrl-class.md) als Datenmember einer Klasse Ansichts- oder Dialogfeldobjekt-Objekt zerstört wird, wenn der Besitzer zerstört wird. Bei Verwendung einer [CListView](../mfc/reference/clistview-class.md), das Framework zerstört das Steuerelement aus, wenn sie die Ansicht zerstört.  
  
 Wenn Sie für Ihre Liste Daten in das Strukturelement-Steuerelement, statt die Anwendung zu speichernde anordnen möchten, müssen Sie für die Aufhebung der Zuordnung anordnen. Weitere Informationen finden Sie unter [Rückrufelemente und Rückrufmaske](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Darüber hinaus sind Sie verantwortlich für das Freigeben von jeder Bilderliste für das, die Sie erstellt und dem Listensteuerelement-Objekt zugeordnet.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

