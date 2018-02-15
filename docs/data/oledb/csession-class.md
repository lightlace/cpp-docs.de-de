---
title: CSession-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs:
- C++
helpviewer_keywords:
- CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3402255bbbfc8e66a55654d91434fa60680a80a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="csession-class"></a>CSession-Klasse
Stellt eine einzelne Datenbank-Access-Sitzung dar.  
  
## <a name="syntax"></a>Syntax

```cpp
class CSession  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Abbrechen](../../data/oledb/csession-abort.md)|Abgebrochen (beendet) der Transaktion.|  
|[Schließen](../../data/oledb/csession-close.md)|Schließt die Sitzung.|  
|[Commit](../../data/oledb/csession-commit.md)|Führt einen Commit die Transaktion.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Gibt Informationen zu einer Transaktion zurück.|  
|[Öffnen](../../data/oledb/csession-open.md)|Öffnet eine neue Sitzung für das Datenquellenobjekt.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Startet eine neue Transaktion für diese Sitzung.|  
  
## <a name="remarks"></a>Hinweise  
 Eine oder mehrere Sitzungen zugeordnet werden jeder anbieterverbindung (Datenquelle) der dargestellt wird, indem Sie eine [CDataSource](../../data/oledb/cdatasource-class.md) Objekt. Zum Erstellen eines neuen `CSession` für eine `CDataSource`, rufen Sie [CSession:: Open](../../data/oledb/csession-open.md). Zum Starten einer Datenbanktransaktion `CSession` bietet die `StartTransaction` Methode. Sobald eine Transaktion gestartet wird, können Sie Sie mithilfe von commit der **Commit** -Methode, oder brechen Sie den Befehl mit der **Abort** Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)