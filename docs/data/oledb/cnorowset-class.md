---
title: CNoRowset-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: e92c9bfb49bbb64faca633f04bb87f40028b6e1e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339561"
---
# <a name="cnorowset-class"></a>CNoRowset-Klasse
Kann als ein Vorlagenargument verwendet werden (`TRowset`) für [CCommand](../../data/oledb/ccommand-class.md) oder [CTable](../../data/oledb/ctable-class.md).  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
### <a name="parameters"></a>Parameter  
 *TAccessor*  
 Ein Accessor-Klasse. Die Standardeinstellung ist `CAccessorBase`.  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CNoRowset` als ein Vorlagenargument, wenn der Befehl kein Rowset zurückgibt.  
  
 `CNoRowset` implementiert die folgenden Stubmethoden, von denen jedes anderen Klassenmethoden Accessor entsprechen:  
  
-   `BindFinished` -Gibt an, wenn die Bindung abgeschlossen ist (gibt `S_OK`).  
  
-   `Close` -Versionen der Zeilen und die aktuelle IRowset-Schnittstelle.  
  
-   `GetIID` -Ruft Sie die Schnittstellen-ID eines Verbindungspunkts ab.  
  
-   `GetInterface` -Ruft eine Schnittstelle ab.  
  
-   `GetInterfacePtr` -Ruft ab einen gekapselten Schnittstellenzeiger auf.  
  
-   `SetAccessor` – Legt fest, die dem Accessor einen Zeiger.  
  
-   `SetupOptionalRowsetInterfaces` – Legt fest, um optionale Schnittstellen für das Rowset.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)