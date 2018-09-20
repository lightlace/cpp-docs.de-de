---
title: 'Ausnahmen: Untersuchen von Ausnahmeinhalten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5fb0df0c16e9aea2f334b6c08f92a3bef4ea486
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378383"
---
# <a name="exceptions-examining-exception-contents"></a>Ausnahmen: Untersuchen von Ausnahmeinhalten

Obwohl eine **catch** des Blocks Argument kann von fast jeden Datentyps, die MFC-Funktionen Auslösen von Ausnahmen von Typen, die von der Klasse abgeleitet `CException`. Um eine von einer MFC-Funktion ausgelöste Ausnahme abzufangen, Sie schreiben eine **catch** blockieren, deren Argument ein Zeiger ist, auf eine `CException` Objekt (oder ein Objekt abgeleitet `CException`, z. B. `CMemoryException`). Überprüfen Sie je nach den genauen Typ der Ausnahme die Datenmember des Ausnahmeobjekts, um Informationen über die genaue Ursache der Ausnahme zu erfassen.

Z. B. die `CFileException` Typ verfügt über die `m_cause` Datenmember, der einen enumerierten Typ enthält, der die Ursache für den Datei-Ausnahme angibt. Einige Beispiele für die möglichen Rückgabewerte sind `CFileException::fileNotFound` und `CFileException::readOnly`.

Das folgende Beispiel zeigt, wie Sie den Inhalt von untersuchen einer `CFileException`. Andere Typen können auf ähnliche Weise untersucht werden.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Weitere Informationen finden Sie unter [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md) und [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

