---
title: CAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9e7f722d4d1759bdec7a23bb15076b38de000eb6
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337416"
---
# <a name="caccessor-class"></a>CAccessor-Klasse
Stellt einen Accessor Typen dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
template <class T>  
class CAccessor : public CAccessorBase, public T  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Die Benutzerdatensatz-Klasse.  
  
## <a name="remarks"></a>Hinweise  
 Sie wird verwendet, wenn ein Datensatz statisch mit einer Datenquelle gebunden ist. Der Datensatz enthält den Puffer. Diese Klasse unterstützt mehrere Accessoren für ein Rowset.  
  
 Verwenden Sie diesen Accessortyp, wenn Sie wissen, dass die Struktur und den Typ der Datenbank.  
  
 Wenn Ihre Accessor Felder enthält, die in den Speicher zu verweisen (wie z. B. eine `BSTR` oder Schnittstelle) muss freigegeben ist, rufen Sie die Memberfunktion [CAccessorRowset:: Freerecordmemory](../../data/oledb/caccessorrowset-freerecordmemory.md) bis zur nächsten Datensatz gelesen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)