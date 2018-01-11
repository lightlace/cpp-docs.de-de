---
title: ExitInstance-Memberfunktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs: C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99898a5e80c3f487c7f53fe81d13d3d1eb55ebd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="exitinstance-member-function"></a>ExitInstance-Memberfunktion
Die [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md) wird jedes Mal aufgerufen, eine Kopie der Anwendung beendet wird, in der Regel als Ergebnis der Benutzer die Anwendung beendet.  
  
 Überschreiben Sie `ExitInstance` Wenn die gewünschte Verarbeitung für spezielle Bereinigung ausführen, z. B. Freigabe von Graphics Device Interface (GDI) Ressourcen oder neuzuweisung von Arbeitsspeicher, die während der Ausführung des Programms verwendet. Bereinigen von Standardelementen wie beispielsweise Dokumente und Ansichten, wird jedoch durch das Framework zusammen mit anderen überschreibbaren Funktionen für spezielle Bereinigungsaktionen auf diese Objekte bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
