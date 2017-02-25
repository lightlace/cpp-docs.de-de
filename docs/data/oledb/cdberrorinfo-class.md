---
title: "CDBErrorInfo-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBErrorInfo"
  - "ATL::CDBErrorInfo"
  - "ATL.CDBErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBErrorInfo-Klasse"
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDBErrorInfo-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet die Unterstützung für OLE DB\-Fehler Verarbeitung mit OLE DB\- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)\-Schnittstelle.  
  
## Syntax  
  
```  
class CDBErrorInfo  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Gibt alle Fehlerinformationen zurückgegeben, die in einem Fehlerdatensatz enthalten sind.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Ruft [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) auf, um grundlegende Informationen zum den angegebenen Fehler zurückgegeben wird.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Aufrufe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx), einen Zeiger auf eine Schnittstelle auf einem benutzerdefinierten Fehlerobjekts zurückzugeben.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Ruft [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) auf, um ein **IErrorInfo**\-Schnittstellenzeiger dem bestimmten Datensatz zurückzukehren.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Ruft [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) auf, um den Fehlerparametern zurückzugeben.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Ruft Fehlerdatensätze für das angegebene Objekt ab.|  
  
## Hinweise  
 Diese Schnittstelle wird mindestens Fehlerdatensätzen den Benutzer zurück.  Rufen Sie zuerst [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) auf, um eine Anzahl Fehlerdatensätze abzurufen.  Rufen Sie dann eine der Zugriffsfunktionen, wie [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md) auf, um Fehlerinformationen für jeden Datensatz abrufen.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)