---
title: 'CDataSource:: GetProperty | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs: C++
helpviewer_keywords: GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96b7437bd96592044b4eab33df3e4912bd677591
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
Gibt den Wert einer angegebenen Eigenschaft für das Quellobjekt verbundenen Daten zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Eine GUID identifiziert den Eigenschaftensatz für die Eigenschaft zurückgegeben werden sollen.  
  
 `propid`  
 [in] Eigenschafts-ID für die Eigenschaft zurückgegeben.  
  
 *pVariant*  
 [out] Ein Zeiger auf die Variante, in denen **GetProperty** gibt den Wert der Eigenschaft zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Abrufen mehrerer Eigenschaften [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)