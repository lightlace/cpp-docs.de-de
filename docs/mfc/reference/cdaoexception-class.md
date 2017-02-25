---
title: "CDaoException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoException class"
  - "Auflistungen, DAO-Fehler"
  - "DAO (Datenzugriffsobjekte), Ausnahmen"
  - "Fehler [C++], DAO"
  - "Errors collection, DAO"
  - "Ausnahmen, in MFC DAO classes"
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahmebedingung dar, die aus den MFC\-Datenbankklassen auf Grundlage Datenzugriffsobjekte \(DAO\) resultiert.  
  
## Syntax  
  
```  
class CDaoException : public CException  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoException::CDaoException](../Topic/CDaoException::CDaoException.md)|Erstellt ein `CDaoException`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)|Gibt die Anzahl der Fehler in der Fehlerauflistung des Datenbankmoduls zurück.|  
|[CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)|EINGABETASTEfehlerinformationen über ein bestimmtes Fehlerobjekt in der Fehlerauflistung.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoException::m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md)|Enthält einen erweiterten Fehlercode für jeden Fehler in den MFC\-DAO\-Klassen.|  
|[CDaoException::m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)|Ein Zeiger auf einen [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md)\-Objekt, das Informationen über ein DAO\-Fehlerobjekt enthält.|  
|[CDaoException::m\_scode](../Topic/CDaoException::m_scode.md)|Der [SCODE](../Topic/CDaoException::m_scode.md) zugeordnete Wert mit dem Fehler.|  
  
## Hinweise  
 Die Klasse enthält öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme bestimmen.  `CDaoException`\-Objekte werden von Memberfunktionen der DAO\-Datenbankklassen erstellt und ausgelöst.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen.  Im Allgemeinen sind die MFC\-Klassen auf Grundlage DAO besser geeignet als die MFC\-Klassen auf Grundlage ODBC; die DAO\-basierten Klassen machen die Daten ein und enthalten durch ODBC\-Treiber, über ein eigenes Datenbankmodul.  Die DAO\-basierten Klassen unterstützen auch Operationen der Datendefinitionssprache \(Data Definition Language\), wie das Hinzufügen von Tabellen zu Klassen, ohne zu müssen, DAO direkt aufzurufen.  Informationen über die Ausnahmen, die durch die ODBC\-Klassen ausgelöst werden, finden Sie unter [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Sie können auf Ausnahmeobjekte im Kontext eines Ausdrucks [ERFASSUNG](../Topic/CATCH.md) zugreifen.  Sie können `CDaoException`\-Objekte aus Ihrem eigenen Code mit der globalen Funktion [AfxThrowDaoException](../Topic/AfxThrowDaoException.md) auslösen.  
  
 In MFC werden alle DAO\-Fehler als Ausnahmen, des Typs `CDaoException` ausgedrückt.  Wenn Sie eine Ausnahme dieses Typs abfangen, können Sie `CDaoException`\-Memberfunktionen verwenden, um Informationen aus allen DAO\-Fehlerobjekten abzurufen, die in der Fehlerauflistung des Datenbankmoduls gespeichert werden.  Während jeder Fehler auftritt, werden eine oder mehrere Fehlerobjekte in die Fehlerauflistung eingefügt.  \(Normalerweise enthält die Auflistung nur ein Fehlerobjekt; Wenn Sie eine ODBC\-Datenquelle verwenden, sind Sie wahrscheinlicher, mehrere Objekte des Fehlers abzurufen.\) Wenn ein anderer DAO\-Vorgang einen Fehler generiert, wird die Fehlerauflistung gelöscht, und das neue Fehlerobjekt wird in die Fehlerauflistung eingefügt.  DAO\-Vorgänge, die keinen Fehler generieren, haben keine Auswirkungen auf die Fehlerauflistung.  
  
 Für DAO\-Fehlercodes finden Sie in der Datei DAOERR.H.  Weitere Informationen finden Sie im Thema "auffangbare Datenzugriffs\-Fehler" in der DAO\-Hilfe.  
  
 Weitere Informationen zur Ausnahmebehandlung im Allgemeinen oder über `CDaoException`\-Objekte, finden Sie in Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  Der zweite Artikel enthält Beispielcode, der Ausnahmebehandlung in DAO veranschaulicht.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)