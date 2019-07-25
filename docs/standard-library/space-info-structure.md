---
title: space_info-Struktur
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: 2a9856746a8bbc796871663a81bd8911d34dcd4a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457556"
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

**Header:** \<Dateisystem >

**Namespace:** std::experimental::filesystem

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md)
