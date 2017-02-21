---
title: "CException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchiveException class, Basisklasse"
  - "CDaoException class, Basisklasse"
  - "CDBException class, Basisklasse"
  - "CException class"
  - "CFileException class, Basisklasse"
  - "CInternetException class, Basisklasse"
  - "CMemoryException class, Basisklasse"
  - "CNotSupportedException class, Basisklasse"
  - "COleDispatchException class, Basisklasse"
  - "COleException class, Basisklasse"
  - "CResourceException class, Basisklasse"
  - "CUserException class"
  - "Ausnahmen, classes for"
  - "Makros, Ausnahmebehandlung"
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für alle Ausnahmen in Microsoft Foundation Class\-Bibliothek.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CException::CException](../Topic/CException::CException.md)|Erstellt ein `CException`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CException::Delete](../Topic/CException::Delete.md)|Löscht ein Objekt `CException`.|  
|[CException::ReportError](../Topic/CException::ReportError.md)|Gibt eine Fehlermeldung in einem Meldungsfeld den Benutzer.|  
  
## Hinweise  
 Da `CException` eine abstrakte Basisklasse ist, können Sie `CException`\-Objekte nicht direkt erstellen; Sie müssen Objekte aus abgeleiteten Klassen erstellen.  Wenn Sie eine eigene Klasse im `CException` erstellen müssen, verwenden Sie eine der abgeleiteten Klassen, die oben als Modell aufgeführt sind.  Überprüfen Sie, ob die abgeleitete Klasse auch `IMPLEMENT_DYNAMIC` verwendet.  
  
 Die abgeleiteten Klassen und ihre Beschreibungen sind nachfolgend aufgeführt:  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Eine Basisklasse für Ressource\-wichtige MFC\-Ausnahmen|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Ungültige ArgumentAusnahmebedingung|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Ausnahme aufgrund ungenügenden Arbeitsspeichers|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Anforderung für einen nicht unterstützten Vorgang|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Archiv\-Besondere Ausnahme|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Datei\-Besondere Ausnahme|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows\-Ressource nicht gefunden oder nicht erstellbar|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE\-Ausnahme|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Datenbankausnahme \(das heißt, Ausnahmebedingungen, die für MFC\-Datenbankklassen auf Grundlage Open Database Connectivity\) auftreten|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Ausnahme OLE\-Dispatchs \(Automatisierung\)|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Ausnahme, die angibt, dass eine Ressource nicht gefunden werden kann|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Datenzugriffsobjektausnahme \(das heißt, Ausnahmebedingungen, die für DAO\-Klassen auftreten\)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Internet\-Ausnahme \(das heißt, Ausnahmebedingungen, die für Internetklassen\) auftreten.|  
  
 Diese Ausnahmen werden vorgesehen, mit den [THROW](../Topic/THROW%20\(MFC\).md), [THROW\_LAST](../Topic/THROW_LAST.md), [TRY](../Topic/TRY.md), [ERFASSUNG](../Topic/CATCH.md), [AND\_CATCH](../Topic/AND_CATCH.md) und [END\_CATCH](../Topic/END_CATCH.md)\-Makros verwendet werden.  Weitere Informationen zu Ausnahmen, finden Sie unter [Ausnahme\-Verarbeiten](../../mfc/reference/exception-processing.md) oder finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
 Um eine bestimmte Ausnahme abzufangen, verwenden Sie die entsprechende abgeleitete Klasse.  Um alle Typen Ausnahmen abzufangen, verwenden Sie `CException` und verwenden Sie dann [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) mit `CException` zu unterscheiden von abgeleitete Klassen.  Beachten Sie, dass `CObject::IsKindOf` funktioniert nur für die Klassen, die mit dem [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)\-Makro deklariert werden, um dynamische Typüberprüfung zu nutzen.  Alle `CException` von abgeleitete Klasse, die Sie erstellen, sollte auch das `IMPLEMENT_DYNAMIC`\-Makro verwenden.  
  
 Sie können Details zu Ausnahmen den Benutzer melden, indem Sie [GetErrorMessage](../Topic/CFileException::GetErrorMessage.md) oder [ReportError](../Topic/CException::ReportError.md), zwei Memberfunktionen bereit aufrufen, die mit allen abgeleiteten Klassen von `CException` funktionieren.  
  
 Wenn eine Ausnahme durch eines der Makros abgefangen wird, wird das Objekt `CException` automatisch gelöscht; löschen Sie es sich nicht.  Wenn eine Ausnahme abgefangen wird, indem ein **catch**\-Schlüsselwort verwendet, wird sie nicht automatisch gelöscht.  Weitere Informationen finden Sie im Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md) weitere Informationen dazu, wann ein exeption Objekt gelöscht werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CException`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Ausnahmeverarbeitung](../../mfc/reference/exception-processing.md)   
 [Wie behebe ich: Erstellen Sie die eigenen benutzerdefinierten Ausnahme\-Klassen?](http://go.microsoft.com/fwlink/?LinkId=128045)