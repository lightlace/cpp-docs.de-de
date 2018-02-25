---
title: 'CArrayRowset:: Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b2dd001dc3946a3eb22b793874ba1f4b16affb72
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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