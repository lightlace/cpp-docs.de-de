---
title: CBookmark-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dba5f98912fc69bac5554a4c6231f77e17e99d98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cbookmark-class"></a>CBookmark-Klasse
Enthält einen Lesezeichenwert in seinem Puffer.  
  
## <a name="syntax"></a>Syntax  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
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
|[Operator =](../../data/oledb/cbookmark-operator-equal.md)|Weist ein `CBookmark` in eine andere Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 **CBookmark\<0 >** ist eine vorlagenspezialisierung der `CBookmark`; der Puffer wird zur Laufzeit dynamisch erstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)