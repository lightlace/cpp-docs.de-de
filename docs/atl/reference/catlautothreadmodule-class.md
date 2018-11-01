---
title: CAtlAutoThreadModule-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: acd277160bc277e919a2802541310aa55446e00c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619712"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule-Klasse

Diese Klasse implementiert einen COM-Server in einem Thread-Pool, Apartment-Modell.

> [!IMPORTANT]
> Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Hinweise

`CAtlAutoThreadModule` leitet sich von [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) und implementiert einen COM-Server in einem Thread-Pool, Apartment-Modell. `CAtlAutoThreadModule` verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) eine Wohnung für jeden Thread im Modul zu verwalten.

Verwenden Sie die [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Makro in Definition der Klasse des Objekts an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als die Klassenfactory. Sie sollten eine einzelne Instanz einer Klasse abgeleitet hinzufügen `CAtlAutoThreadModuleT` wie z. B. `CAtlAutoThreadModule`. Zum Beispiel:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Diese Klasse ersetzt die veraltete [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[CAtlAutoThreadModuleT-Klasse](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
