---
title: Austauschen von Daten | Microsoft Docs
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
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 172b03278ceede44f06b846c8b4f066e9f141e3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exchanging-data"></a>Datenaustausch
Wie bei den meisten Dialogfelder, ist der Austausch von Daten zwischen dem Eigenschaftenblatt und der Anwendung eine der wichtigsten Funktionen des Eigenschaftsblatts an. Dieser Artikel beschreibt, wie Sie diese Aufgabe ausführen.  
  
 Austauschen von Daten mit einem Eigenschaftenblatt wird tatsächlich durch Austausch von Daten mit den einzelnen Eigenschaftenseiten der Eigenschaftenseite. Das Verfahren zum Austauschen von Daten mit einer Eigenschaftenseite entspricht derjenigen Austauschen von Daten mit einem Dialogfeld, da ein [CPropertyPage](../mfc/reference/cpropertypage-class.md) Objekt ist ein spezieller [CDialog](../mfc/reference/cdialog-class.md) Objekt. Die Prozedur nutzt das Framework Dialogfeld Daten Dialogdatenaustausch (DDX) Funktion, die Daten zwischen Steuerelementen in einem Dialogfeld und den Membervariablen des Objekts Box Dialogfeld austauscht.  
  
 Der wichtige Unterschied zwischen Austauschen von Daten mit einem Eigenschaftenblatt und einem normalen Dialogfeld ist, dass das Eigenschaftenblatt mehrere Seiten verwenden, damit Sie Daten mit aller Seiten im Eigenschaftenblatt austauschen müssen. Weitere Informationen über DDX, finden Sie unter [Dialogdatenaustausch und-Validierung](../mfc/dialog-data-exchange-and-validation.md).  
  
 Im folgende Beispiel werden beim Austausch von Daten zwischen einer Ansicht und zwei Seiten eines Eigenschaftenblatts veranschaulicht:  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)

