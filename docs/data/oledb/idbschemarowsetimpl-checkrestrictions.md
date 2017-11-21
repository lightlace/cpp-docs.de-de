---
title: 'IDBSchemaRowsetImpl:: Checkrestrictions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
dev_langs: C++
helpviewer_keywords: CheckRestrictions method
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d6e057c56e824327d726e073a02f0fa636553c40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="idbschemarowsetimplcheckrestrictions"></a>IDBSchemaRowsetImpl::CheckRestrictions
Überprüft die Gültigkeit von Einschränkungen an einem Schemarowset.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CheckRestrictions(  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `rguidSchema`  
 [in] Ein Verweis auf die angeforderte Schemarowset-GUID (z. B. `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [in] Die Anzahl der Einschränkungen, die der Consumer für das Schemarowset übergeben hat.  
  
 `rgRestrictions`  
 [in] Ein Längenarray von *cRestrictions* von festzulegenden Einschränkungswerten. Weitere Informationen finden Sie in der Beschreibung des `rgRestrictions` -Parameters in [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `CheckRestrictions` , um die Gültigkeit von Einschränkungen für ein Schemarowset zu überprüfen. Es überprüft die Einschränkungen für `DBSCHEMA_TABLES`-, **DBSCHEMA_COLUMNS**- und **DBSCHEMA_PROVIDER_TYPES** -Schemarowsets. Rufen Sie es auf, um zu ermitteln, ob der Aufruf eines Consumers von **IDBSchemaRowset::GetRowset** richtig ist. Wenn Sie andere als die oben aufgeführten Schemarowsets unterstützen möchten, sollten Sie Ihre eigene Funktion zum Ausführen dieser Aufgabe erstellen.  
  
 `CheckRestrictions` bestimmt, ob der Consumer [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) mit der richtigen Einschränkung und dem richtigen Einschränkungstyp aufruft (z. B. `VT_BSTR` für eine Zeichenfolge), die der Anbieter unterstützt. Es bestimmt außerdem, ob die richtige Anzahl von Einschränkungen unterstützt werden. Standardmäßig fragt `CheckRestrictions` den Anbieter mittels des Aufrufs von [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) , welche Einschränkungen für ein angegebenes Rowset unterstützt werden. Es vergleicht dann die Einschränkungen vom Consumer mit den vom Anbieter unterstützten, wobei der Vergleich entweder erfolgreich ist oder fehlschlägt.  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBSchemaRowsetImpl-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl-Klasse, Elemente](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset-Klassen und Typedef-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)