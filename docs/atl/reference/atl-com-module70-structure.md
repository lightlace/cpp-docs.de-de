---
title: _ATL_COM_MODULE70-Struktur
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: c6361fc5374ed732cd9ccbfbbd1d3d1c2fc8f1f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261038"
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70-Struktur

Ein, die COM-bezogenem Code in ATL

## <a name="syntax"></a>Syntax

```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>Member

`cbSize`<br/>
Die Größe der Struktur, die für die versionsverwaltung verwendet werden soll.

`m_hInstTypeLib`<br/>
Die Handle-Instanz, auf die Typbibliothek für dieses Modul.

`m_ppAutoObjMapFirst`<br/>
Die Adresse des Arrayelements dar, der angibt, der des Anfang der Objekt-Zuordnungseinträge für dieses Modul.

`m_ppAutoObjMapLast`<br/>
Die Adresse des Arrayelements dar, der angibt, des Ende der Objekt-Zuordnungseinträge für dieses Modul.

`m_csObjMap`<br/>
Kritischen Abschnitt, um die Serialisierung des Zugriffs auf der Objekt-Zuordnungseinträge. Wird intern verwendet, von ATL

## <a name="remarks"></a>Hinweise

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) als Typdefinition von _ATL_COM_MODULE70 definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../../atl/reference/atl-classes.md)
