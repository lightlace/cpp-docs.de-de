---
title: 'IRowsetChangeImpl:: FlushData | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs: C++
helpviewer_keywords: FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31555e1f8305a281955902b71fdc71fbcc5405e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
Außer Kraft gesetzt, vom Anbieter, um Daten an seinen Speicher zu übertragen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hRowToFlush*  
 [in] Handle für die Zeilen für die Daten. Der Typ dieser Zeile wird bestimmt, aus der *RowClass* Vorlagenargument von der `IRowsetImpl` Klasse (`CSimpleRow` standardmäßig).  
  
 *hAccessorToFlush*  
 [in] Handle für die Zugriffsmethode, die Bindungsinformationen und Typinformationen im enthält seine **PROVIDER_MAP** (siehe [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetChangeImpl-Klasse](../../data/oledb/irowsetchangeimpl-class.md)