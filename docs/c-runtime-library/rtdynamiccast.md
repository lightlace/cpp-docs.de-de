---
title: __RTDynamicCast | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __RTDynamicCast
apilocation:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- __RTDynamicCast
dev_langs:
- C++
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85f8b31ee9faec433fa0c9f1ff64d5bfa1e9665a
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161254"
---
# <a name="rtdynamiccast"></a>__RTDynamicCast

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

## <a name="remarks"></a>Hinweise

Konvertiert ein Objekt vom Typ `inptr` in Typ `TargetType`. Der `inptr`-Typ muss ein Zeiger sein, wenn `TargetType` ein Zeiger ist, oder ein lvalue, wenn `TargetType` ein Verweis ist. `TargetType` muss ein Zeiger oder ein Verweis auf einen zuvor definierten Klassentyp oder ein Zeiger auf „void“ sein.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|