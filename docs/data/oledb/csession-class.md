---
title: "CSession-Klasse"
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
  - "CSession"
  - "ATL::CSession"
  - "ATL.CSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession-Klasse"
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CSession-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine einzelne Datenbankzugriffssitzung dar.  
  
## Syntax  
  
```  
class CSession  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Abort](../../data/oledb/csession-abort.md)|Bricht die Transaktion ab \(beendet sie\).|  
|[Schließen](../../data/oledb/csession-close.md)|Schließt die Sitzung.|  
|[Commit ausführen](../../data/oledb/csession-commit.md)|Führt ein Commit der Transaktion aus.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Gibt Informationen bezüglich eine Transaktion zurückgesetzt.|  
|[Öffnen](../../data/oledb/csession-open.md)|Öffnet eine neue Sitzung für das Datenquellenobjekt.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Startet eine neue Transaktion für diese Sitzung.|  
  
## Hinweise  
 Eine oder mehrere Sitzungen können mit jeder Anbieter\-Verbindung \(Datenquelle\) zugeordnet werden, die durch [Ableiten](../../data/oledb/cdatasource-class.md) ein Objekt dargestellt wird.  Um eine neue `CSession` für `CDataSource` zu erstellen, rufen Sie [CSession::Open](../../data/oledb/csession-open.md) auf.  Um eine Datenbanktransaktion zu beginnen, stellt `CSession` die `StartTransaction`\-Methode.  Sobald eine Transaktion gestartet wird, können Sie mit der **Commit**\-Methode weitergeben, oder brechen Sie diese mithilfe der **Abbrechen**\-Methode ab.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [CatDB](../../top/visual-cpp-samples.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)