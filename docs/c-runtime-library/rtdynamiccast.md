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
ms.openlocfilehash: 90c68ed56b52b57deb234717b3b95ec197d26318
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450933"
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
 `inptr`  
 Zeiger auf ein polymorphes Objekt.  
  
 `VfDelta`  
 Offset des virtuellen Funktionszeiger im Objekt.  
  
 `SrcType`  
 Statischer Objekttyp, auf den der `inptr`-Parameter zeigt.  
  
 `TargetType`  
 Beabsichtigtes Ergebnis der Umwandlung.  
  
 `isReference`  
 `true`, wenn die Eingabe ein Verweis ist. `false`, wenn die Eingabe ein Zeiger ist.  
  
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