---
title: CComModule-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlAutoThreadModule
- CAtlAutoThreadModule
- ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 09f4a7061ce1e4a09d0d27bd90dfcc16a37f4d5b
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodule-class"></a>CComModule-Klasse
Diese Klasse implementiert einen COM-Server in einem Thread-Pool, Apartment-Modell.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Hinweise  
 `CAtlAutoThreadModule`leitet sich von [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) und einen Thread Pool, Apartmentmodell COM-Server implementiert. `CAtlAutoThreadModule`verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) ein Apartment für jeden Thread im Modul zu verwalten.  
  
 Verwenden Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) Makro in die Klassendefinition für das Objekt an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als ClassFactory. Sie sollten eine einzelne Instanz einer Klasse, die von abgeleiteten hinzufügen `CAtlAutoThreadModuleT` wie z. B. `CAtlAutoThreadModule`. Zum Beispiel:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Diese Klasse ersetzt die veraltete [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlAutoThreadModuleT-Klasse](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
