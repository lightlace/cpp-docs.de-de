---
title: 'IDBSchemaRowsetImpl:: GetSchemas | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs: C++
helpviewer_keywords: GetSchemas method
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce07c59eb9dd806d2f297591e8f3b389b3f4ce54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplgetschemas"></a>IDBSchemaRowsetImpl::GetSchemas
Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD ( GetSchema s )(  
   ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pcSchemas*  
 [out] Ein Zeiger auf eine **ULONG** , die mit der Anzahl von Schemas gefüllt ist.  
  
 *prgSchemas*  
 [out] Ein Zeiger auf ein Array von GUIDs, das mit einem Zeiger auf ein Array von Schemarowset-GUIDs gefüllt ist.  
  
 *prgRest*  
 [out] Ein Zeiger auf ein Array von **ULONG**s, das mit dem Einschränkungsarray gefüllt werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode gibt ein Array aller Schemarowsets zurück, die vom Anbieter unterstützt werden. Finden Sie unter [IDBSchemaRowset:: GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) im Windows SDK.  
  
 Für die Implementierung dieser Funktion muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mithilfe der Schemazuordnungsinformationen antwortet die Funktion dann mit dem Array von GUIDs für die Schemas in der Zuordnung. Dies stellt die Schemas dar, die vom Anbieter unterstützt werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl-Klasse, Elemente](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset:: GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)