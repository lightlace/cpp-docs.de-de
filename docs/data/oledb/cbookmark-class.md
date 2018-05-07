---
title: CBookmark-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c14fde6fb07a35ef9e2955ce61f991bede6b11a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cbookmark-class"></a>CBookmark-Klasse
Enthält einen Lesezeichenwert in seinem Puffer.  
  
## <a name="syntax"></a>Syntax

```cpp
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase
  
template <>  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### <a name="parameters"></a>Parameter  
 `nSize`  
 Die Größe des Lesezeichenpuffers in Bytes. Wenn `nSize` NULL ist, der Puffer Lesezeichen wird zur Laufzeit dynamisch erstellt werden.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|Der Konstruktor|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|Ruft die Zeiger auf den Puffer ab.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Ruft die Größe des Puffers in Bytes ab.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Legt den Lesezeichenwert.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cbookmark-operator-equal.md)|Weist ein `CBookmark` in eine andere Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 **CBookmark\<0 >** ist eine vorlagenspezialisierung der `CBookmark`; der Puffer wird zur Laufzeit dynamisch erstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)