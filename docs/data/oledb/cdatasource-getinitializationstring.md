---
title: 'CDataSource:: Getinitializationstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
dev_langs: C++
helpviewer_keywords: GetInitializationString method
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0cc70e9cb1c775cf9c19f7269a5305624d27210b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourcegetinitializationstring"></a>CDataSource::GetInitializationString
Ruft die Initialisierungszeichenfolge einer Datenquelle, die derzeit geöffnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *pInitializationString*  
 [out] Ein Zeiger auf die Initialisierungszeichenfolge angibt.  
  
 *bIncludePassword*  
 [in] **"true"** Wenn Zeichenfolge ein Kennwort; enthält andernfalls **"false"**.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die resultierende Initialisierungszeichenfolge kann verwendet werden, um diese datenquellenverbindung später erneut zu öffnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)