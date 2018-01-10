---
title: 'CRowset:: Getoriginaldata | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.GetOriginalData
- CRowset<TAccessor>::GetOriginalData
- GetOriginalData
- ATL::CRowset<TAccessor>::GetOriginalData
- ATL.CRowset.GetOriginalData
- CRowset::GetOriginalData
- ATL::CRowset::GetOriginalData
- CRowset.GetOriginalData
dev_langs: C++
helpviewer_keywords: GetOriginalData method
ms.assetid: 5b69d30e-34f4-41a4-a82d-cd175be88d53
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b1799ce2ead7d3369fa1d4b81a8a6553b37f1ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetgetoriginaldata"></a>CRowset::GetOriginalData
Aufrufe **IRowsetUpdate::GetOriginalData** zum Abrufen der Daten, die zuletzt aus dem Verbindungspool abgerufen oder an die Datenquelle übertragen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT GetOriginalData( ) throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Daten zuletzt aus dem Verbindungspool abgerufen oder an die Datenquelle übertragen ab; Er ruft keine Werte auf Grundlage ausstehende Änderungen ab.  
  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetUpdate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Sie müssen auch festlegen **DBPROP_IRowsetUpdate** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx)