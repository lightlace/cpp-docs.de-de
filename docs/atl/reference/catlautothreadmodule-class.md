---
title: CComModule-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c89d142254909591ebd01bfa859be5488cbfaf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356617"
---
# <a name="catlautothreadmodule-class"></a>CComModule-Klasse
Diese Klasse implementiert einen Thread Pool, Apartmentmodell COM-Server.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Hinweise  
 `CAtlAutoThreadModule` leitet sich von [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) und einen Thread Pool, Apartmentmodell COM-Server implementiert. `CAtlAutoThreadModule` verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) einem Apartment für jeden Thread im Modul zu verwalten.  
  
 Verwenden Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Makro in die Objektklassendefinition an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als ClassFactory. Sie sollten eine einzelne Instanz einer Klasse abgeleitet wurde. Klicken Sie dann hinzufügen `CAtlAutoThreadModuleT` wie z. B. `CAtlAutoThreadModule`. Zum Beispiel:  
  
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
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
