---
title: ExitInstance-Memberfunktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 954d2248061ec571d9d2ba8804c1f7c97275cbfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343498"
---
# <a name="exitinstance-member-function"></a>ExitInstance-Memberfunktion
Die [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md) wird jedes Mal aufgerufen, eine Kopie der Anwendung beendet wird, in der Regel als Ergebnis der Benutzer die Anwendung beendet.  
  
 Überschreiben Sie `ExitInstance` Wenn die gewünschte Verarbeitung für spezielle Bereinigung ausführen, z. B. Freigabe von Graphics Device Interface (GDI) Ressourcen oder neuzuweisung von Arbeitsspeicher, die während der Ausführung des Programms verwendet. Bereinigen von Standardelementen wie beispielsweise Dokumente und Ansichten, wird jedoch durch das Framework zusammen mit anderen überschreibbaren Funktionen für spezielle Bereinigungsaktionen auf diese Objekte bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
