---
title: Testen von Internetanwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [MFC], testing
- debugging Web applications [MFC], testing applications
- testing [MFC], Internet applications
- debugging [MFC], Web applications
- Internet debugging and testing
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
ms.openlocfilehash: 934d336f8c7544bafa412a7b52404a657e8dc9ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439363"
---
# <a name="testing-internet-applications"></a>Testen von Internetanwendungen

Es gibt einige spezielle Herausforderungen für die testen im Internet, insbesondere für Anwendungen, die auf einem Webserver ausgeführt. Die ersten Tests wahrscheinlich erfolgt über einen Einzelbenutzer-Client eine Verbindung herstellen, auf einem Testserver. Dies ist nützlich zum Debuggen von Code sein.

Sie werden auch unter realen Bedingungen testen möchten: mit mehreren Clients über schnelle Verbindungen als auch niedrigen Geschwindigkeit serieller Leitungen verbunden sind, einschließlich Modem-Verbindungen. Es kann schwierig sein, simulieren echte Bedingungen, aber es lohnt sich sicherlich verbringt Zeit Entwerfen von möglichen Szenarien und dort ausgeführt werden. Wenn möglich, werden Sie auch Tools für Kapazitäts- und Belastungstests verwenden möchten. Bestimmte Klassen von Fehlern, z. B. Fehler der zeitlichen Steuerung, sind nur schwer zu finden und zu reproduzieren.

Eine der Herausforderungen der Internet-Programmierung ist die Sichtbarkeit. Viele Zugriffe auf Ihre Website möglicherweise Ihre Server verlangsamen. Sie möchten Ihren Server, um Ihre Anforderungen ordnungsgemäß herabstufen. Sie möchten etwas zu vermeiden, die für den Computer eines Benutzers sein kann, wenn Ihre Anwendung (z. B. die Beschädigung von Daten beim Schreiben in die Registrierung oder beim Schreiben von Cookies auf dem Client) ein Fehler auftritt.

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

