---
title: "Ausnahmeklassen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ausnahmeklassen"
  - "Ausnahmebehandlung, Ausnahmeklassen"
  - "MFC, Ausnahmen"
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmeklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klassenbibliothek stellt einen Mechanismus für die Ausnahmenbehandlung auf der Klasse `CException`.  Das Anwendungsframework verwendet Ausnahmen im Code; Sie können in den auch verwenden.  Weitere Informationen finden Sie im Artikel [Ausnahmen](../mfc/exception-handling-in-mfc.md).  Sie können eigene Ausnahmetypen von `CException` ableiten.  
  
 MFC stellt einer Ausnahmeklasse, von der Sie die eigene Ausnahme sowie Ausnahmeklassen für alle Ausnahmen, berechnen können, die sie unterstützt.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Die Basisklasse für Ausnahmen.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Eine Archivausnahme.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler in einem DAO\-Datenbank\-Vorgang.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler beim ODBC\-Datenbankverarbeiten.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Eine dateiorientierten Ausnahme.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Eine Ausnahme aufgrund ungenügenden Arbeitsspeichers.  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Eine Ausnahme, erstellten mit einer nicht unterstützten Funktion.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Eine Ausnahme, erstellten aus einem Fehler beim OLE\-Verarbeiten.  Diese Klasse wird von Container und Server verwendet.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Eine Ausnahme, erstellten von einem Fehler bei der Automatisierung.  Automatisierungsausnahmen werden durch Automatisierungsserver ausgelöst und abgefangen von den Automatisierungsclients.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Eine Ausnahme, erstellten einer, sondern eine Windows\-Ressource zu laden.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Eine Ausnahme verwendet, um einen selbst eingeleiteten Vorgang zu beenden.  In der Regel ist der Benutzer vom Problem benachrichtigt wurde, bevor diese Ausnahme ausgelöst wird.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)