---
title: __RTDynamicCast
ms.date: 11/04/2016
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: c4b0caadf20d6c5494acf47ee5a788b5ee009c47
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957343"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

Laufzeitimplementierung des [dynamic_cast](../cpp/dynamic-cast-operator.md)-Operators.

## <a name="syntax"></a>Syntax

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>Parameter

*inptr*<br/>
Zeiger auf ein polymorphes Objekt.

*VfDelta*<br/>
Offset des virtuellen Funktionszeiger im Objekt.

*SrcType*<br/>
Statischer Objekttyp, auf den der `inptr`-Parameter zeigt.

*TargetType*<br/>
Beabsichtigtes Ergebnis der Umwandlung.

*isReference*<br/>
**true**, wenn die Eingabe ein Verweis ist. **false**, wenn die Eingabe ein Zeiger ist.

## <a name="return-value"></a>Rückgabewert

Zeiger auf das entsprechende Unterobjekt, wenn erfolgreich; andernfalls **NULL**.

## <a name="exceptions"></a>Ausnahmen

`bad_cast()`, wenn die Eingabe für `dynamic_cast<>` ein Verweis ist und die Umwandlung fehlschlägt.

## <a name="remarks"></a>Anmerkungen

Konvertiert ein Objekt vom Typ `inptr` in Typ `TargetType`. Der `inptr`-Typ muss ein Zeiger sein, wenn `TargetType` ein Zeiger ist, oder ein lvalue, wenn `TargetType` ein Verweis ist. `TargetType` muss ein Zeiger oder ein Verweis auf einen zuvor definierten Klassentyp oder ein Zeiger auf „void“ sein.

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|