---
title: 'Ausnahmen: Untersuchen von Ausnahmeinhalten'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
ms.openlocfilehash: 4355a575f29741d0c7b9f1e12e40ca9d977219b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630068"
---
# <a name="exceptions-examining-exception-contents"></a>Ausnahmen: Untersuchen von Ausnahmeinhalten

Obwohl eine **catch** des Blocks Argument kann von fast jeden Datentyps, die MFC-Funktionen Auslösen von Ausnahmen von Typen, die von der Klasse abgeleitet `CException`. Um eine von einer MFC-Funktion ausgelöste Ausnahme abzufangen, Sie schreiben eine **catch** blockieren, deren Argument ein Zeiger ist, auf eine `CException` Objekt (oder ein Objekt abgeleitet `CException`, z. B. `CMemoryException`). Überprüfen Sie je nach den genauen Typ der Ausnahme die Datenmember des Ausnahmeobjekts, um Informationen über die genaue Ursache der Ausnahme zu erfassen.

Z. B. die `CFileException` Typ verfügt über die `m_cause` Datenmember, der einen enumerierten Typ enthält, der die Ursache für den Datei-Ausnahme angibt. Einige Beispiele für die möglichen Rückgabewerte sind `CFileException::fileNotFound` und `CFileException::readOnly`.

Das folgende Beispiel zeigt, wie Sie den Inhalt von untersuchen einer `CFileException`. Andere Typen können auf ähnliche Weise untersucht werden.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md) und [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

