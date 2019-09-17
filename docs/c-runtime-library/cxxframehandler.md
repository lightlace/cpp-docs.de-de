---
title: __CxxFrameHandler
ms.date: 11/04/2016
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: 4cb5ae10d4281c4a7167db7adf4ea6788ad3e3c0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944504"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

Interne CRT-Funktion. Wird von CRT verwendet, um Frames für strukturierte Ausnahmen zu verarbeiten.

## <a name="syntax"></a>Syntax

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>Parameter

*pExcept*<br/>
Ausnahmeaufzeichnung, die an die möglichen `catch`-Anweisungen übergeben wird.

*pRN*<br/>
Dynamische Informationen über den Stapelrahmen, der zur Verarbeitung der Ausnahme verwendet wird. Weitere Informationen finden Sie unter ehdata.h.

*pContext*<br/>
Kontext. (Wird bei Intel-Prozessoren nicht verwendet.)

*pDC*<br/>
Zusätzliche Informationen über den Funktionsstart und den Stapelrahmen.

## <a name="return-value"></a>Rückgabewert

Einer der *Filterausdruckswerte*, die von der [try-except-Anweisung](../cpp/try-except-statement.md) verwendet werden.

## <a name="remarks"></a>Anmerkungen

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|