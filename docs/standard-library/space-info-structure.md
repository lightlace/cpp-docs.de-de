---
title: space_info-Struktur
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: b6998f4ac7ced2d85063186edbd47227b6d24ca5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399446"
---
# <a name="spaceinfo-structure"></a>space_info-Struktur

Enthält Informationen zu einem Volume.

## <a name="syntax"></a>Syntax

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>Member

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|`unsigned long long capacity`|Gibt die Gesamtanzahl der Bytes an, die vom Volume dargestellt werden können.|
|`unsigned long long free`|Gibt die Anzahl der Bytes an, die nicht zum Darstellen der Daten auf dem Volume verwendet werden.|
|`unsigned long long available`|Gibt die Anzahl der Bytes an, die zum Darstellen der Daten auf dem Volume verfügbar sind.|

## <a name="requirements"></a>Anforderungen

**Header:** \<filesystem>

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)<br/>
