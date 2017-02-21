---
title: "CDBException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDBException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBException class"
  - "database exceptions [C++]"
  - "Fehler [C++], Datenbank"
  - "exceptions [C++], Datenbank"
  - "ODBC-Klassen [C++], Ausnahmen"
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDBException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Ausnahmebedingung dar, die aus den Datenbankklassen entsteht.  
  
## Syntax  
  
```  
  
class CDBException : public CException  
  
```  
  
## Mitglieder  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDBException::m\_nRetCode](../Topic/CDBException::m_nRetCode.md)|Enthält einen Rückgabecode der Open Database Connectivity \(ODBC\), des Typs **RETCODE**.|  
|[CDBException::m\_strError](../Topic/CDBException::m_strError.md)|Enthält eine Zeichenfolge, die den Fehler in den alphanumerischen Begriffen beschreibt.|  
|[CDBException::m\_strStateNativeOrigin](../Topic/CDBException::m_strStateNativeOrigin.md)|Enthält eine Zeichenfolge, die den Fehler im Hinblick auf die Fehlercodes beschrieben, die von ODBC zurückgegeben werden.|  
  
## Hinweise  
 Die Klasse enthält zwei öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme bestimmen oder eine Textmeldung anzuzeigen, die die Ausnahme beschreibt.  `CDBException`\-Objekte werden von Memberfunktionen der Datenbankklassen erstellt und ausgelöst.  
  
> [!NOTE]
>  Diese Klasse ist eine von Klassen MFC Open Database Connectivity \(ODBC\).  Wenn Sie stattdessen die neueren Klassen der Datenzugriffsobjekte \(DAO\) verwenden, verwenden Sie stattdessen [CDaoException](../../mfc/reference/cdaoexception-class.md).  Alle DAO\-Klassen\-Namen haben "CDao" als Präfix.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Ausnahmen sind die Fälle nicht ordnungsgemäßen Ausführung Bedingungen außerhalb des Steuerelements des Programms, wie Datenquelle oder Netzwerk E\/A\-Fehler mit einbeziehend.  Fehler, die Sie normalerweise, im normalen Verlauf der Ausführung des Programms zu finden, normalerweise werden nicht als Ausnahmen.  
  
 Sie können auf diese Objekte im Rahmen eines Ausdrucks **CATCH** zugreifen.  Sie können `CDBException`\-Objekte aus Ihrem eigenen Code mit der globalen Funktion `AfxThrowDBException` auslösen.  
  
 Weitere Informationen zur Ausnahmebehandlung im Allgemeinen oder über `CDBException`\-Objekte, finden Sie in Artikel [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## Anforderungen  
 **Header:**  afxdb.h  
  
## Siehe auch  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [AfxThrowDBException](../Topic/AfxThrowDBException.md)   
 [CRecordset::Update](../Topic/CRecordset::Update.md)   
 [CRecordset::Delete](../Topic/CRecordset::Delete.md)   
 [CException Class](../../mfc/reference/cexception-class.md)