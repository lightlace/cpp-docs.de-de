---
title: IConvertTypeImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0dfa073226dc4ddb3cd14b2aae31375a6f6ccc25
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269782"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl-Klasse
Stellt eine Implementierung der [IConvertType](https://msdn.microsoft.com/library/ms715926.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IConvertTypeImpl`.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CanConvert](#canconvert)|Erhalten Informationen über die Verfügbarkeit von typkonvertierungen für einen Befehl oder in einem Rowset.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist obligatorisch. Befehle, Rowsets und Indexes-Schemarowsets. `IConvertTypeImpl` implementiert die Schnittstelle durch delegieren, auf das Konvertierungsobjekt von OLE DB bereitgestellt.  

## <a name="canconvert"></a> Iconverttypeimpl:: CanConvert
Erhalten Informationen über die Verfügbarkeit von typkonvertierungen für einen Befehl oder in einem Rowset.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(CanConvert)(DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IConvertType::CanConvert](https://msdn.microsoft.com/library/ms711224.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Verwendet OLE DB-Datenkonvertierung in `MSADC.DLL`.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
