---
title: 'Ausnahmen: Auslösen von Ausnahmen in eigenen Funktionen'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: 030bf3db9ff305f35cbfb0b518c8704114ce083d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405858"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>Ausnahmen: Auslösen von Ausnahmen in eigenen Funktionen

Es ist möglich, das Paradigma der MFC-Ausnahmebehandlung verwenden ausschließlich zum Abfangen von Ausnahmen, die von den Funktionen in MFC oder andere Bibliotheken ausgelöst. Zusätzlich zum Abfangen von Ausnahmen von Bibliothekscode, können Sie Ausnahmen aus Ihrem eigenen Code auslösen, wenn Sie Funktionen schreiben, die außergewöhnliche Bedingungen, die auftreten können.

Wenn eine Ausnahme ausgelöst wird, die Ausführung der aktuellen Funktion beendet wird und springt direkt an die **catch** Block des Frames, innere Ausnahme. Der Ausnahmemechanismus umgeht den normalen Beendigung Pfad von einer Funktion. Aus diesem Grund muss sichergestellt werden, die Speicherblöcke zu löschen, die in einer normalen Beendigung gelöscht werden würde.

#### <a name="to-throw-an-exception"></a>Eine Ausnahme ausgelöst

1. Verwenden Sie eine der MFC-Hilfsfunktionen, z. B. `AfxThrowMemoryException`. Diese Funktionen lösen einen vorab festgelegten Exception-Objekt des entsprechenden Typs.

   Im folgenden Beispiel wird eine Funktion versucht, zwei Speicherblöcke zuzuordnen, und löst eine Ausnahme aus, wenn entweder Zuordnung fehlschlägt:

   [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   Wenn die erste Zuordnung fehlschlägt, können Sie einfach die Arbeitsspeicher-Ausnahme auslösen. Wenn die erste Zuordnung erfolgreich ist, aber das zweite Argument ein Fehler auftritt, müssen Sie die Zuordnung ist den ersten Block freigeben, vor dem Auslösen der Ausnahme. Wenn beide belegungen erfolgreich sind, können Sie normalerweise fortgesetzt und die Blöcke frei, wenn die Funktion beendet wird.

     - ODER

1. Verwenden Sie eine benutzerdefinierte Ausnahme, um eine Problem-Bedingung anzugeben. Sie können ein Element eines beliebigen Typs, sogar eine ganze Klasse als Ausnahme auslösen.

   Im folgenden Beispiel wird versucht, einen Sound wiederzugeben, über ein Waveformgerät und löst eine Ausnahme aus, wenn ein Fehler auftritt.

   [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
>  MFC Standardbehandlung von Ausnahmen gilt nur für Verweise auf `CException` Objekte (und Objekte des `CException`-abgeleiteten Klassen). Im obigen Beispiel wird MFCs-Ausnahmemechanismus umgangen werden.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)
