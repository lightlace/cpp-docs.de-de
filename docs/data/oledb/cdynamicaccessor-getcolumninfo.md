---
title: 'CDynamicAccessor:: GetColumnInfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs: C++
helpviewer_keywords: GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ece75eeb539dff60b29396e3076cd2465571453a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRowset`  
 [in] Ein Zeiger auf die [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) Schnittstelle.  
  
 *pColumns*  
 [out] Ein Zeiger auf Speicher, in dem die Anzahl der Spalten im Rowset zurückgegeben werden soll; Diese Zahl umfasst die Lesezeichenspalte, sofern vorhanden.  
  
 *ppColumnInfo*  
 [out] Ein Zeiger auf Speicher, in dem ein Array von zurückgegeben **DBCOLUMNINFO** Strukturen. Finden Sie unter "DBCOLUMNINFO-Strukturen" in [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE DB Programmer's Reference*.  
  
 `ppStringsBuffer`  
 [out] Ein Zeiger auf Speicher, in dem einen Zeiger auf Speicher für alle Zeichenfolgenwerte zurückgegeben (Namen verwendet, entweder innerhalb der *Columnid* oder *PwszName*) innerhalb eines einzelnen zuordnungsblocks.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE DB Programmer's Reference* Informationen zu den Datentypen **DBORDINAL**, **DBCOLUMNINFO**, und **OLECHAR**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)