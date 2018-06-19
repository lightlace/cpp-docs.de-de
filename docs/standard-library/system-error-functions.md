---
title: '&lt;system_error&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 6135a3dc51b372c85545f01f52c70cbc6f236e64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855132"
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
|`_Errno`|Der im Fehlercodeobjekt zu speichernde Enumeration-Wert.|

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
|`_Errno`|Der im Fehlerzustandobjekt zu speichernde Enumeration-Wert.|

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
