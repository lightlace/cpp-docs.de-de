---
title: CBulkRowset-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7dddf645b8795b12f6da70081327366b62946303
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090724"
---
# <a name="cbulkrowset-class"></a>CBulkRowset-Klasse
Abruft, und Bearbeiten von Zeilen, die auf Daten in einer Massenoperation zu arbeiten, indem mehrere Zeilenhandles mit einem einzigen Aufruf abgerufen.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein Accessorklasse.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Inkrementiert den Verweiszähler dieser Planergruppe.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Konstruktor.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Ruft die erste Zeile der Daten, einen neuen Bulk-Abruf bei Bedarf ausführen.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Wechselt zur letzten Zeile.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Ruft die nächste Datenzeile ab.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Wechselt zur vorherigen Zeile.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Ruft die von einer Textmarke markierte Zeile oder die Zeile an einem angegebenen Offset aus diesem Lesezeichen ab.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Ruft Zeilen ab der ein Bruchteilen Position im Rowset ab.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Legt die aktuelle Zeile (**M_nCurrentRow**) auf 0 (null) und Versionen, die alle Zeilen.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Legt die Anzahl von Zeilenhandles durch einen Aufruf abgerufen werden sollen.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von der `CBulkRowset` Klasse.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)