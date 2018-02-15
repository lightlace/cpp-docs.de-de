---
title: CSimpleRow-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c241118d13f7efecef9413851d3d47ff9a08b58
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="csimplerow-class"></a>CSimpleRow-Klasse
Stellt eine Standardimplementierung für das Zeilenhandle, im dient der [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax

```cpp
class CSimpleRow  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Fügt einen Verweiszähler für eine vorhandene Zeilenhandle an.|  
|[Compare](../../data/oledb/csimplerow-compare.md)|Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|Der Konstruktor.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Gibt Zeilen frei.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Der Verweiszähler für eine vorhandene Zeilenhandle.|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|Ein Index in das Rowset, das den Cursor darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile. `IRowsetImpl` erstellt ein neues `CSimpleRow` für jede Zeile im angeforderten [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` kann auch durch Ihre eigene Implementierung der das Zeilenhandle ersetzt werden, entspricht ein Standardvorlagenargument zu `IRowsetImpl`. Die einzige Anforderung zum Ersetzen von dieser Klasse ist, haben Sie die Klasse einen Konstruktor bereitstellen, die einen einzelnen Parameter vom Typ akzeptiert **lang**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)