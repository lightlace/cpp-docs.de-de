---
title: ISessionPropertiesImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ISessionPropertiesImpl
dev_langs: C++
helpviewer_keywords: ISessionPropertiesImpl class
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f8824ac2081ffd214402a23c6a5975e027ecf9ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl-Klasse
Stellt eine Implementierung von der [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `ISessionPropertiesImpl`.  
  
 `PropClass`  
 Eine benutzerdefinierbare Eigenschaftsklasse, die standardmäßig `T`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Gibt die Liste der Eigenschaften in der Sitzung-Eigenschaftengruppe, die derzeit für die Sitzung festgelegt werden.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Legt die Eigenschaften in der Eigenschaftengruppe Sitzung fest.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für Sitzungen. Diese Klasse implementiert Sitzungseigenschaften durch eine statische Funktion definiert, die durch Aufrufen der [Satz eigenschaftenzuordnung](../../data/oledb/begin-propset-map.md). Die Satz eigenschaftenzuordnung sollte in Ihrer Sitzungsklasse angegeben werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)