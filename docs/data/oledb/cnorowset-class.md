---
title: CNoRowset-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CNoRowset
- ATL::CNoRowset<TAccessor>
- CNoRowset
- ATL.CNoRowset<TAccessor>
- ATL::CNoRowset
dev_langs:
- C++
helpviewer_keywords:
- CNoRowset class
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87d005dc19ef286bc4b0da927ecabcd90e6f0235
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098159"
---
# <a name="cnorowset-class"></a>CNoRowset-Klasse
Kann als ein Vorlagenargument verwendet werden (`TRowset`) für [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Ein Accessorklasse. Die Standardeinstellung ist `CAccessorBase`.  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CNoRowset` als ein Vorlagenargument, wenn der Befehl kein Rowset zurückgibt.  
  
 `CNoRowset` implementiert die folgenden Stubmethoden, von denen jedes anderen Methoden des Eigenschaftenaccessors Klasse entsprechen:  
  
-   **BindFinished** -gibt an, wann die Bindung abgeschlossen ist (gibt `S_OK`).  
  
-   **Schließen** -frei, Zeilen und die aktuelle IRowset-Schnittstelle.  
  
-   `GetIID` -Ruft die Schnittstellen-ID von einem Verbindungspunkt ab.  
  
-   **GetInterface** -Schnittstelle abruft.  
  
-   `GetInterfacePtr` -Ruft einen gekapselten Schnittstellenzeiger ab.  
  
-   **SetAccessor** -legt einen Zeiger auf den Accessor fest.  
  
-   **SetupOptionalRowsetInterfaces** -optionale Schnittstellen für Rowset richtet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)