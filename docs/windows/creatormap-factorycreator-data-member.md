---
title: 'Creatormap:: FactoryCreator-Datenmember | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs:
- C++
helpviewer_keywords:
- factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 29a88c34502404de13bd3b93d13c60470e2882ea
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650715"
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator-Datenmember
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
### <a name="parameters"></a>Parameter  
 *currentflags*  
 Eines der [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.  
  
 *entry*  
 Eine CreatorMap.  
  
 *iidClassFactory*  
 Die Schnittstellen-ID von einer Klassenfactory.  
  
 *Factory*  
 Wenn der Vorgang abgeschlossen ist, die Adresse einer Klassenfactory.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Erstellt eine Factory für die angegebene CreatorMap an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [CreatorMap-Struktur](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)