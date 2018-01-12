---
title: 'IDBSchemaRowsetImpl:: | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
dev_langs: C++
helpviewer_keywords: GetRowset method
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5164bcd56c61868649af6185c8b84ebf20098b18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplgetrowset"></a>IDBSchemaRowsetImpl::GetRowset
Gibt ein Schemarowset zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD (GetRowset)(  
   IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pUnkOuter`  
 [in] Ein äußeres **IUnknown** beim Aggregieren, andernfalls **NULL**.  
  
 `rguidSchema`  
 [in] Ein Verweis auf die angeforderte Schemarowset-GUID (z. B. `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] Die Anzahl der Einschränkungen, die auf das Schemarowset angewendet werden sollen.  
  
 `rgRestrictions`  
 [in] Ein Array von `cRestrictions`**VARIANT**s, die die Einschränkungen darstellen.  
  
 `riid`  
 [in] Die anzufordernde IID des neu erstellten Schemarowsets.  
  
 `cPropertySets`  
 [in] Die Anzahl der festzulegenden Eigenschaftensätze.  
  
 `rgPropertySets`  
 [in/out] Ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) -Strukturen, die für das neu erstellte Schemarowset festgelegt werden sollen.  
  
 `ppRowset`  
 [out] Ein Zeiger auf die angeforderte Schnittstelle für das neu erstellte Schemarowset.  
  
## <a name="remarks"></a>Hinweise  
 Für diese Methode muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mit den Schemazuordnungsinformationen erstellt `GetRowset` ein angegebenes Rowsetobjekt, wenn der `rguidSchema` -Parameter mit einem der Zuordnungseintrags-GUIDs identisch ist. Unter [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) finden Sie eine Beschreibung des Zuordnungseintrags.  
  
 Finden Sie unter [IDBSchemaRowset:: GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl-Klasse, Elemente](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl:: GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)