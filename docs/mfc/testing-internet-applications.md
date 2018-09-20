---
title: Testen von Internetanwendungen | Microsoft-Dokumentation
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
ms.openlocfilehash: 518fbe754b676798c6d2acc2a3e26ea1d3e3d4ac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444153"
---
# <a name="testing-internet-applications"></a>Testen von Internetanwendungen

Es gibt einige spezielle Herausforderungen für die testen im Internet, insbesondere für Anwendungen, die auf einem Webserver ausgeführt. Die ersten Tests wahrscheinlich erfolgt über einen Einzelbenutzer-Client eine Verbindung herstellen, auf einem Testserver. Dies ist nützlich zum Debuggen von Code sein.

Sie werden auch unter realen Bedingungen testen möchten: mit mehreren Clients über schnelle Verbindungen als auch niedrigen Geschwindigkeit serieller Leitungen verbunden sind, einschließlich Modem-Verbindungen. Es kann schwierig sein, simulieren echte Bedingungen, aber es lohnt sich sicherlich verbringt Zeit Entwerfen von möglichen Szenarien und dort ausgeführt werden. Wenn möglich, werden Sie auch Tools für Kapazitäts- und Belastungstests verwenden möchten. Bestimmte Klassen von Fehlern, z. B. Fehler der zeitlichen Steuerung, sind nur schwer zu finden und zu reproduzieren.

Eine der Herausforderungen der Internet-Programmierung ist die Sichtbarkeit. Viele Zugriffe auf Ihre Website möglicherweise Ihre Server verlangsamen. Sie möchten Ihren Server, um Ihre Anforderungen ordnungsgemäß herabstufen. Sie möchten etwas zu vermeiden, die für den Computer eines Benutzers sein kann, wenn Ihre Anwendung (z. B. die Beschädigung von Daten beim Schreiben in die Registrierung oder beim Schreiben von Cookies auf dem Client) ein Fehler auftritt.

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

