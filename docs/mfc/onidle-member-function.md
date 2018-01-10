---
title: OnIdle-Memberfunktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnIdle
dev_langs: C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dfbc0a1f20cb6cc01143ed6f07a63e84b53be6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="onidle-member-function"></a>OnIdle-Memberfunktion
Wenn keine Windows-Meldungen verarbeitet werden, das Framework Ruft die [CWinApp](../mfc/reference/cwinapp-class.md) Memberfunktion [OnIdle](../mfc/reference/cwinapp-class.md#onidle) (beschrieben in der Verweis auf die MFC-Bibliothek).  
  
 Überschreiben Sie `OnIdle` Hintergrundaufgaben ausführen. Die Standardversion aktualisiert den Zustand von Benutzeroberflächenobjekten z. B. Schaltflächen der Symbolleiste und führt die Bereinigung von temporären Objekten, die vom Framework im Verlauf seiner Vorgänge erstellt. Die folgende Abbildung veranschaulicht, wie die Nachrichtenschleife aufruft `OnIdle` Wenn in der Warteschlange keine Nachrichten vorhanden sind.  
  
 ![Nachricht schleifenprozess](../mfc/media/vc387c1.gif "vc387c1")  
Nachrichtenschleife  
  
 Weitere Informationen zu den Schritten, die Sie in der Leerlaufschleife ausführen können, finden Sie unter [Leerlaufschleifen-Verarbeitung](../mfc/idle-loop-processing.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
