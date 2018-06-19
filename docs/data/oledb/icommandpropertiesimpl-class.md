---
title: ICommandPropertiesImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 25be1548bd41f832a007f102c138fc01f8818774
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099000"
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
|[getProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|Gibt die Liste der Eigenschaften in der Rowset-Eigenschaftengruppe, die derzeit für das Rowset angefordert werden.|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|Legt die Eigenschaften in der Rowset-Eigenschaftengruppe fest.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist obligatorisch einschaltbefehle. Die Implementierung erfolgt durch eine statische Funktion definiert, indem Sie die [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) Makro.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)