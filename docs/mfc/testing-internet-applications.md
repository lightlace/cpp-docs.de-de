---
title: Testen von Internetanwendungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61ffc5b11783806555b210b8561cbe6cdd2878ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="testing-internet-applications"></a>Testen von Internetanwendungen
Einige eindeutige Tests ausgabebefehlsstruktur treten im Internet, insbesondere für Anwendungen, die auf einem Webserver ausgeführt. Die ersten Tests wahrscheinlich erfolgt über einen Einzelbenutzer-Client Herstellen einer Verbindung mit einem Testserver. Dies wird für das Debuggen von Code hilfreich sein.  
  
 Sie werden auch unter realen Bedingungen testen möchten: durch mehrere Clients über schnelle Verbindungen sowie niedriger Übertragungsrate serieller Leitungen verbunden sind, einschließlich Modem Verbindungen. Es kann schwierig sein, realen Bedingungen zu simulieren, aber es lohnt sich sicherlich Ausgaben Zeit entwerfen möglichen Szenarien und dort ausgeführt werden. Wenn möglich, sollten Sie auch Tools zur Kapazitäts- und Belastungstests verwenden. Bestimmte Klassen von Fehlern, z. B. ein Timeout-Fehlern und sind schwer zu finden und zu reproduzieren.  
  
 Eine der Herausforderungen der internetprogrammierung ist seine Sichtbarkeit. Ihre Server möglicherweise viele Zugriffe auf Ihrer Website verlangsamen. Sie möchten Ihre Server kontrolliert beeinträchtigt wird. Möchten nichts zu vermeiden, die auf dem Computer eines Benutzers sein kann, wenn die Anwendung (z. B. Beschädigung von Daten beim Schreiben in die Registrierung oder beim Schreiben von Cookies auf dem Client) kann nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

