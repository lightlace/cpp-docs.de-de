---
title: CDBErrorInfo-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 26ed1bdaff6746e74029111dae0ce1abc0ea7493
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo-Klasse
Bietet Unterstützung für OLE DB-Fehler beim Verarbeiten, die mit dem OLE DB- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDBErrorInfo  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Gibt alle Fehlerinformationen, die in einen Fehlerdatensatz enthalten sind.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Aufrufe [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) grundlegende Informationen zu dem angegebenen Fehler zurückgegeben.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Aufrufe [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) auf einen Zeiger auf eine Schnittstelle für ein Objekt für die benutzerdefinierte Fehlermeldung zurückzugeben.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Aufrufe [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) zurückzugebenden ein **IErrorInfo** Schnittstellenzeiger auf den angegebenen Datensatz.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Aufrufe [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) der Fehlerparameter zurückgegeben.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Ruft die Error-Datensätze für das angegebene Objekt ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle zurückgegeben ein oder mehrere Error-Datensätze an den Benutzer. Rufen Sie [cdberrorinfo:: Geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) zuerst, Anzahl der Error-Datensätze. Dann aufzurufen, die eine des Zugriffs Funktionen, wie z. B. [cdberrorinfo:: Getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), um Fehlerinformationen für jeden Datensatz abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)