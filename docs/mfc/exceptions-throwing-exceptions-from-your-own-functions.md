---
title: "Ausnahmen: Ausnahmen in eigenen Funktionen auslösen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff189a255fe9e3c54ac4c15fbea43dcf8d8a2b12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>Ausnahmen: Ausnahmen in eigenen Funktionen auslösen
Es ist möglich, mit dem MFC-Ausnahmebehandlung Paradigma ausschließlich zum Abfangen von Ausnahmen, die von Funktionen in MFC oder anderen Bibliotheken ausgelöst. Zusätzlich zum Abfangen von Ausnahmen, die ausgelöst wird, von dem Bibliothekscode, können Sie aus Ihrem eigenen Code Ausnahmen auslösen, wenn Sie Funktionen schreiben, die Ausnahmebedingungen auftreten können.  
  
 Wenn eine Ausnahme ausgelöst wird, die Ausführung der aktuellen Funktion beendet, und springt direkt an die **catch** Block des innersten Ausnahme Frames. Der Ausnahmemechanismus umgeht den normalen Beendigung Pfad von einer Funktion. Aus diesem Grund muss sicherstellen, dass diese Speicherblöcke gelöscht, die in einer normalen Beendigung gelöscht würden.  
  
#### <a name="to-throw-an-exception"></a>Eine Ausnahme auslöst.  
  
1.  Verwenden Sie eine der MFC-Hilfsfunktionen, z. B. `AfxThrowMemoryException`. Diese Funktionen lösen ein vorab Ausnahmeobjekt des entsprechenden Typs.  
  
     Im folgenden Beispiel wird eine Funktion versucht, zwei Speicherblöcke belegen, und löst eine Ausnahme aus, wenn entweder Zuordnung ein Fehler auftritt:  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     Wenn es sich bei die erste Zuordnung ein Fehler auftritt, können Sie einfach die Arbeitsspeicher-Ausnahme auslösen. Wenn es sich bei die erste Zuordnung erfolgreich ist, jedoch dem zweiten Ausdruck ein Fehler auftritt, müssen Sie die erste zuordnungsblocks freigeben, vor dem Auslösen der Ausnahme. Wenn beide belegungen erfolgreich sind, können Sie normal fortgesetzt und freier Blöcke beim Beenden der Funktion.  
  
     - ODER  
  
2.  Verwenden Sie eine benutzerdefinierte Ausnahme, um ein Problem mit Problem hindeuten. Sie können ein Element eines beliebigen Typs, sogar eine ganze Klasse als Ausnahme auslösen.  
  
     Im folgenden Beispiel wird versucht, Abspielen eines Sounds über eine Waveformgerät und löst eine Ausnahme aus, wenn ein Fehler auftritt.  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  MFC Standardbehandlung von Ausnahmen gilt nur für Zeiger auf `CException` Objekte (und Objekte eines `CException`-abgeleitete Klassen). Das obige Beispiel umgeht MFCs-Ausnahmemechanismus.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

