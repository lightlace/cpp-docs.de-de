---
title: "Erstellen von nicht modalen Dialogfeldern"
ms.custom: na
ms.date: "12/03/2016"
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
  - "MFC-Dialogfelder, Erstellen"
  - "MFC-Dialogfelder, Nicht modal"
  - "Nicht modale Dialogfelder, Erstellen"
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen von nicht modalen Dialogfeldern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein nicht modales Dialogfeld müssen Sie die eigenen öffentlichen Konstruktor in der Dialogfeldklasse bereitstellen.  Um ein nicht modales Dialogfeld zu erstellen, rufen Sie den öffentlichen Konstruktor auf und rufen Sie dann die [Erstellen](../Topic/CDialog::Create.md)\-Memberfunktion des Dialogfeldobjekts auf die Dialogfeldressource zu laden.  Sie können **Erstellen** entweder während oder nach dem Konstruktoraufruf aufrufen.  Wenn die Dialogfeldressource die Eigenschaft **WS\_VISIBLE** hat, wird das Dialogfeld sofort.  Falls nicht, müssen Sie die zugehörige Memberfunktion [ShowWindow](../Topic/CWnd::ShowWindow.md) aufrufen.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)