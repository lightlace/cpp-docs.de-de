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
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 565b971b53ddb0a50b276d76aaaf62e9f7fa39f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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