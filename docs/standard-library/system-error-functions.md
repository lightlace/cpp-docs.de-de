---
title: '&lt;System_error&gt;-Funktionen'
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 78be83af678b553babbf1cde3d96c1507940b611
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412110"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;System_error&gt;-Funktionen

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|||

## <a name="generic_category"></a> generic_category

Stellt die Kategorie für allgemeine Fehler dar.

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>Hinweise

Die `generic_category` Objekt ist eine Implementierung von [Error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a> make_error_code

Erstellt ein Fehlercodeobjekt.

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>Parameter

*error*\
Die `std::errc` im fehlercodeobjekt zu speichernde Enumerationswert.

### <a name="return-value"></a>Rückgabewert

Das Fehlercodeobjekt.

### <a name="remarks"></a>Hinweise

## <a name="make_error_condition"></a> make_error_condition

Erstellt ein Fehlerzustandobjekt.

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>Parameter

*error*\
Die `std::errc` im fehlercodeobjekt zu speichernde Enumerationswert.

### <a name="return-value"></a>Rückgabewert

Das Fehlerzustandobjekt.

### <a name="remarks"></a>Hinweise

## <a name="system_category"></a> system_category

Stellt die Kategorie für Fehler dar, die von Low-Level-Systemüberläufen verursacht wurden.

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>Hinweise

Die `system_category` Objekt ist eine Implementierung von [Error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Siehe auch

[\<system_error>](../standard-library/system-error.md)<br/>
