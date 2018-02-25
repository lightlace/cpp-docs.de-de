---
title: CAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs:
- C++
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1f0e893f300b7d89bee14ce28490328979d0fa17
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="caccessor-class"></a>CAccessor-Klasse
Stellt einen Accessor Typen dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
template <class T>  
class CAccessor : public CAccessorBase, public T  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Benutzerdatensatz-Klasse.  
  
## <a name="remarks"></a>Hinweise  
 Wird verwendet, wenn ein Datensatz statisch mit einer Datenquelle gebunden ist. Der Datensatz enthält den Puffer. Diese Klasse unterstützt mehrere Accessoren für ein Rowset.  
  
 Verwenden Sie diesen Accessortyp, wenn Sie wissen, dass die Struktur und den Typ der Datenbank.  
  
 Wenn der Accessor Felder enthält, die in den Arbeitsspeicher zu verweisen (z. B. eine `BSTR` oder Schnittstelle) sein muss freigegeben ist, rufen Sie die Memberfunktion [CAccessorRowset:: Freerecordmemory](../../data/oledb/caccessorrowset-freerecordmemory.md) vor der nächsten Datensatz gelesen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)