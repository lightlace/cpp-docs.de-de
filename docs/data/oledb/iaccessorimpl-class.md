---
title: IAccessorImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d62deeb487fded5895bbd47332a0f8a6ad7bbce6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl-Klasse
Stellt eine Implementierung von der [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Rowset- oder Object-Klasse.  
  
 `BindType`  
 Storage-Einheit für die Bindungsinformationen. Die Standardeinstellung ist die **ATLBINDINGS** Struktur (siehe "Atldb.h").  
  
 `BindingVector`  
 Storage-Einheit für die Spalteninformationen. Die Standardeinstellung ist [CAtlMap](../../atl/reference/catlmap-class.md) , in dem das Schlüsselelement ist ein **HACCESSOR** Wert und das Value-Element ist ein Zeiger auf eine `BindType` Struktur.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Der Konstruktor.|  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Fügt einen Verweiszähler für einen vorhandenen Accessor.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Erstellt einen Accessor aus einem Satz von Bindungen.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Gibt die Bindungen in einem Accessor zurück.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Gibt einen Accessor frei.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist erforderlich für Rowsets und Befehle. OLE DB benötigt Anbietern zum Implementieren einer **HACCESSOR**, dies ist ein Tag auf ein Array von [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) Strukturen. **HACCESSOR**s gebotenen `IAccessorImpl` sind Adressen von der `BindType` Strukturen. Standardmäßig `BindType` ist definiert als eine **ATLBINDINGS** in `IAccessorImpl`der Vorlagendefinition. `BindType` bietet einen Mechanismus, der von verwendeten `IAccessorImpl` verfolgen die Anzahl von Elementen in seiner **DBBINDING** array sowie eine Referenz Count "und"-Accessor-Flags.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)