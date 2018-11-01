---
title: 'Ausnahmen: OLE-Ausnahmen'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: 2732f571d305fda2b739be02661ab9558f8bc653
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515415"
---
# <a name="exceptions-ole-exceptions"></a>Ausnahmen: OLE-Ausnahmen

Die Techniken und Funktionen für die Behandlung von Ausnahmen in OLE sind identisch mit denen für andere Ausnahmen zu behandeln. Weitere Informationen zur Behandlung von Ausnahmen, finden Sie im Artikel [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).

Alle Exception-Objekte werden von der abstrakten Basisklasse abgeleitet `CException`. MFC stellt zwei Klassen für die Behandlung von OLE-Ausnahmen:

- [COleException](../mfc/reference/coleexception-class.md) für die Behandlung allgemeiner OLE-Ausnahmen.

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) für das Erstellen und behandeln (Automatisierung) Ausnahmen verteilen.

Der Unterschied zwischen diesen beiden Klassen ist die Menge an Informationen bieten, und wo sie verwendet werden. `COleException` verfügt über einen öffentlichen Datenmember, der den OLE-Statuscode für die ausgelöste Ausnahme enthält. `COleDispatchException` Stellt Weitere Informationen, einschließlich der folgenden:

- Einen anwendungsspezifischen Fehlercode

- Einen Fehler, Beschreibung, wie z. B. "Datenträger voll"

- Einen Hilfekontext, den Ihre Anwendung verwenden können, um zusätzliche Informationen für den Benutzer bereitzustellen

- Der Name der Hilfedatei von Ihrer Anwendung

- Der Name der Anwendung, die die Ausnahme generiert hat

`COleDispatchException` enthält weitere Informationen, sodass sie mit Produkten wie Microsoft Visual Basic verwendet werden kann. Die verbale fehlerbeschreibung kann in einem Meldungsfeld oder einer sonstigen Benachrichtigung verwendet werden. die Hilfeinformationen kann verwendet werden, auf denen der Benutzer auf die Bedingungen zu reagieren, die die Ausnahme verursacht hat.

Zwei globale Funktionen entsprechen den zwei Klassen des OLE-Ausnahme: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) und [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Verwenden sie zum bzw. allgemeiner OLE-Ausnahmen und OLE-Dispatch-Ausnahmen auslösen.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

