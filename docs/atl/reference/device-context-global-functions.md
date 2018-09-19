---
title: Globale Gerätekontext-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac2e56e4b13f739f61df5b37ab70689784a39882
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077541"
---
# <a name="device-context-global-functions"></a>Globale Gerätekontext-Funktionen

Diese Funktion erstellt einen Gerätekontext für ein bestimmtes Gerät.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Erstellt einen Gerätekontext.|

##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC

Erstellt einen Gerätekontext für das Gerät mit dem angegeben wird, der [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Struktur.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Parameter

*hdc*<br/>
[in] Das vorhandene Handle einen Gerätekontext, oder NULL.

*ptd*<br/>
[in] Ein Zeiger auf die `DVTARGETDEVICE` -Struktur, die Informationen über das Zielgerät enthält.

### <a name="return-value"></a>Rückgabewert

Gibt das Handle für einen Gerätekontext für das Gerät mit dem angegeben wird, der `DVTARGETDEVICE`. Wenn kein Gerät angegeben ist, gibt das Handle zurück, auf dem Standardgerät für die Anzeige.

### <a name="remarks"></a>Hinweise

Wenn die Struktur NULL ist und *Hdc* NULL ist, erstellt einen Gerätekontext für das Standard-Anzeigegerät.

Wenn *Hdc* ist nicht NULL und *Ptd* NULL ist, die Funktion gibt die vorhandene *Hdc*.  

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
