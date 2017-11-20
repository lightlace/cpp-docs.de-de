---
title: IConvertTypeImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
dev_langs: C++
helpviewer_keywords: IConvertTypeImpl class
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 293d5d02b9515db7356eb839ced8dc1d006daafb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl-Klasse
Stellt eine Implementierung von der [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IConvertTypeImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|Erhalten Informationen über die Verfügbarkeit von typkonvertierungen aus, auf einen Befehl oder für ein Rowset.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle ist verbindlich auf Befehle, Rowsets und Index-Rowsets. **IConvertTypeImpl** implementiert die Schnittstelle, indem Sie auf die vom OLE DB-Konvertierungsobjekt delegieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)