---
title: Ausnahmeklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: 99a2764dcad15267b1aab8a60951f99f21352726
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392868"
---
# <a name="exception-classes"></a>Ausnahmeklassen

Die Class-Bibliothek bietet ein Verfahren zur Ausnahmebehandlung basierend auf Klasse `CException`. Das Anwendungsframework verwendet Ausnahmen im Code. Sie können auch in Ihrer verwenden. Weitere Informationen finden Sie im Artikel [Ausnahmen](../mfc/exception-handling-in-mfc.md). Sie können Ihre eigenen Ausnahmetypen aus ableiten `CException`.

MFC enthält eine Ausnahmeklasse, die von der Sie Ihre eigene Ausnahme abgeleitet werden können sowie Ausnahmeklassen für alle Ausnahmen, die es unterstützt.

[CException](../mfc/reference/cexception-class.md)<br/>
Die Basisklasse für Ausnahmen.

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Ausnahme "Archiv".

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Eine Ausnahme, die nach einem Fehler in einem DAO-Datenbank-Vorgang.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Eine Ausnahme, die sich aus einem Fehler bei der Verarbeitung der ODBC-Datenbank ergeben.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Eine Ausnahme dateiorientierte.

[CMemoryException](../mfc/reference/cmemoryexception-class.md)<br/>
Eine Out-of-Memory-Ausnahme.

[CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)<br/>
Eine Ausnahme, die durch eine nicht unterstützte Funktion verwenden.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Eine Ausnahme, die nach einem Fehler bei der Verarbeitung von OLE. Diese Klasse wird von sowohl Container und Server verwendet.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Eine Ausnahme aufgrund eines Fehlers bei der Automatisierung. Automation-Ausnahmen werden vom Automatisierungsserver ausgelöst und abgefangen, die von Benutzeroberflächenautomatisierungs-Clients.

[CResourceException](../mfc/reference/cresourceexception-class.md)<br/>
Eine Ausnahme, die nach einem Fehler, eine Windows-Ressource zu laden.

[CUserException](../mfc/reference/cuserexception-class.md)<br/>
Eine Ausnahme verwendet, um einen vom Benutzer initiierte Vorgang zu beenden. Der Benutzer hat in der Regel des Problems benachrichtigt wurde, bevor diese Ausnahme ausgelöst wird.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
