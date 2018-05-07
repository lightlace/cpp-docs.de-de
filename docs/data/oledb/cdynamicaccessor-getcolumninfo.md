---
title: 'CDynamicAccessor:: GetColumnInfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c9fe862f08fc9ecfa280dcbb55f48e14427d6ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetColumnInfo(IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer) throw();  
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