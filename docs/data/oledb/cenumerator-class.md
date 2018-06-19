---
title: CEnumerator-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b7e390212da53f85cb50dd5bb151ea6740784b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096105"
---
# <a name="cenumerator-class"></a>CEnumerator-Klasse
Verwendet eine OLE DB-Enumerator-Objekt, das macht die [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) -Schnittstelle zur Rückgabe eines Rowsets, die alle Datenquellen und Enumeratoren beschreibt.  
  
## <a name="syntax"></a>Syntax

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Suchen](../../data/oledb/cenumerator-find.md)|Durchsucht verfügbaren Anbieter (Datenquellen) mit dem angegebenen Namen gesucht.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Ruft die `IMoniker` Schnittstelle für den aktuellen Datensatz.|  
|[Öffnen](../../data/oledb/cenumerator-open.md)|Öffnet den Enumerator.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können Abrufen der **ISourcesRowset** Daten indirekt von dieser Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)