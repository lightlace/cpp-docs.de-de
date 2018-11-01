---
title: '&lt;System_error&gt;-Funktionen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 24890830456e3c1026b02960aa650a43da3b6067
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554383"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;System_error&gt;-Funktionen

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a> generic_category

Stellt die Kategorie für allgemeine Fehler dar.

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>Hinweise

Die `generic_category` Objekt ist eine Implementierung von [Error_category](../standard-library/error-category-class.md).

## <a name="make_error_code"></a> make_error_code

Erstellt ein Fehlercodeobjekt.

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Errno*|Der im Fehlercodeobjekt zu speichernde Enumeration-Wert.|

### <a name="return-value"></a>Rückgabewert

Das Fehlercodeobjekt.

### <a name="remarks"></a>Hinweise

## <a name="make_error_condition"></a> make_error_condition

Erstellt ein Fehlerzustandobjekt.

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Errno*|Der im Fehlerzustandobjekt zu speichernde Enumeration-Wert.|

### <a name="return-value"></a>Rückgabewert

Das Fehlerzustandobjekt.

### <a name="remarks"></a>Hinweise

## <a name="system_category"></a> system_category

Stellt die Kategorie für Fehler dar, die von Low-Level-Systemüberläufen verursacht wurden.

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Hinweise

Die `system_category` Objekt ist eine Implementierung von [Error_category](../standard-library/error-category-class.md).

## <a name="see-also"></a>Siehe auch

[<system_error>](../standard-library/system-error.md)<br/>
