---
title: ICommandPropertiesImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36c524d8aae9223e47b39bfe6cbfdfafdaa006f6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl-Klasse
Stellt eine Implementierung von der [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Klasse abgeleitet wurde.  
  
 `PropClass`  
 Die Eigenschaftenklasse.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Gibt die Liste der Eigenschaften in der Rowset-Eigenschaftengruppe, die derzeit für das Rowset angefordert werden.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Legt die Eigenschaften in der Rowset-Eigenschaftengruppe fest.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist obligatorisch einschaltbefehle. Die Implementierung erfolgt durch eine statische Funktion definiert, indem Sie die [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) Makro.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)