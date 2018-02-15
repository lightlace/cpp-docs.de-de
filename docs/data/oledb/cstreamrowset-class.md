---
title: CStreamRowset-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4e499d732beb2d73dbb6ec0bbe0b360eeb394b9d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cstreamrowset-class"></a>CStreamRowset-Klasse
Verwendet eine `CCommand` oder `CTable` Deklaration.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein Accessorklasse.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|Konstruktor. Instanziiert und initialisiert die `CStreamRowset` Objekt.|  
|[Schließen](../../data/oledb/cstreamrowset-close.md)|Versionen der [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) Schnittstellenzeiger in der Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CStreamRowset` in Ihrer `CCommand` oder `CTable` Deklaration, z. B.:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 oder  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` Gibt eine `ISequentialStream` -Zeiger ist, die in gespeichert ist `m_spStream`. Verwenden Sie dann die **lesen** Methode zum Abrufen der Daten (Unicode-Zeichenfolge) im XML-Format. Zum Beispiel:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 führt die XML-Formatierung und gibt alle Spalten und Zeilen des Rowsets als eine XML-Zeichenfolge zurück.  
  
> [!NOTE]
>  Dieses Feature funktioniert nur mit SQL Server 2000.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)