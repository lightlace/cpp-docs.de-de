---
title: __CxxFrameHandler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- __CxxFrameHandler
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __CxxFrameHandler
dev_langs:
- C++
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4141d932cfad78ca9c563334ebbe51f711153e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088721"
---
# <a name="cxxframehandler"></a>__CxxFrameHandler

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

## <a name="remarks"></a>Hinweise

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h, ehdata.h|