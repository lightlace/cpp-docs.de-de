---
title: Ausnahmeklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.exception
dev_langs:
- C++
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce4085d0f5f2dcc73d126d04b7560ef8360ffd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exception-classes"></a>Ausnahmeklassen
Die Klassenbibliothek bietet einen Mechanismus zur Ausnahmebehandlung basierend auf der Klasse `CException`. Das Anwendungsframework verwendet Ausnahmen im Code. Sie können auch in Ihre verwenden. Weitere Informationen finden Sie im Artikel [Ausnahmen](../mfc/exception-handling-in-mfc.md). Sie können eigene Ausnahmetypen aus ableiten `CException`.  
  
 MFC enthält eine Ausnahmeklasse, die von der Sie eine eigene Ausnahme abgeleitet werden können sowie Ausnahmeklassen für alle Ausnahmen, die es unterstützt.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Die Basisklasse für Ausnahmen.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Eine Ausnahme Archiv.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Eine Ausnahme aufgrund eines Fehlers im eine Datenbankoperation DAO.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Eine Ausnahme, die nach einem Fehler bei der Verarbeitung der ODBC-Datenbank.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Eine Datei-orientierte-Ausnahme.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Eine Out-of-Memory-Ausnahme.  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Eine Ausnahme, die aus der Verwendung einer nicht unterstützten Funktion.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, die resultierenden nach einem Fehler bei der OLE-Verarbeitung. Diese Klasse wird von Container und Server.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Eine Ausnahme aufgrund eines Fehlers während der Automatisierung. Automation-Ausnahmen werden von Automatisierungsserver ausgelöst und abgefangen von-Clients.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Eine Ausnahme aufgrund eines Fehlers beim Laden einer Windows-Ressource.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Eine Ausnahme verwendet, um einen Benutzer initiierten Vorgang zu beenden. In der Regel hat der Benutzer des Problems benachrichtigt wurde, bevor diese Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

