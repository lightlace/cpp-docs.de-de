---
title: 'CRowset:: GetDataHere | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::GetDataHere
- CRowset<TAccessor>.GetDataHere
- CRowset.GetDataHere
- GetDataHere
- CRowset::GetDataHere
- ATL::CRowset::GetDataHere
- ATL::CRowset<TAccessor>::GetDataHere
- ATL.CRowset<TAccessor>.GetDataHere
- ATL.CRowset.GetDataHere
dev_langs:
- C++
helpviewer_keywords:
- GetDataHere method
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bcd5a70702a2b38fcdc97b431bfdd29a01c60ddf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetgetdatahere"></a>CRowset::GetDataHere
Ruft Daten aus der aktuellen Zeile ab, und platziert es in den angegebenen Puffer.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT GetDataHere(int nAccessor,   
  void* pBuffer) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Indexnummer des Accessors für den Zugriff auf die Daten verwenden.  
  
 `pBuffer`  
 [out] Ein Puffer, in dem die Daten für den aktuellen Datensatz platziert werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Beispiel zur Verwendung dieser Funktion finden Sie unter der [MultiRead-Beispiel](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)