---
title: 'CArrayRowset:: Operator | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755e484f430f47eb072e3c590bfbee8471984bb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
Stellt arrayähnlichen Syntax für den Zugriff auf eine Zeile im Rowset bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein aus einer Vorlage gebildete-Parameter, der angibt, den Typ des Accessors im Rowset gespeichert.  
  
 `nRow`  
 [in] Die Nummer der Zeile (Arrayelement) Sie zugreifen möchten.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Inhalt der angeforderte Zeile.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `nRow` überschreitet die Anzahl der Zeilen im Rowset, wird eine Ausnahme ausgelöst.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CArrayRowset-Klasse](../../data/oledb/carrayrowset-class.md)