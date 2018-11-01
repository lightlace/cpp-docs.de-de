---
title: _CxxThrowException
ms.date: 11/04/2016
apiname:
- _CxxThrowException
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: 925b72a120b31029b76fa38bee73eea003511cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550331"
---
# <a name="cxxthrowexception"></a>_CxxThrowException

Erstellt den Ausnahmedatensatz und ruft die Laufzeitumgebung auf, um die Verarbeitung der Ausnahme zu starten.

## <a name="syntax"></a>Syntax

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>Parameter

*pExceptionObject*<br/>
Das Objekt, durch das die Ausnahme erzeugt wurde.

*pThrowInfo*<br/>
Die zum Verarbeiten der Ausnahme erforderlichen Informationen.

## <a name="remarks"></a>Hinweise

Diese Methode ist in einer compilerspezifischen Datei enthalten, die vom Compiler zum Verarbeiten von Ausnahmen verwendet wird. Rufen Sie die Methode nicht direkt aus Ihrem Code auf.

## <a name="requirements"></a>Anforderungen

**Quelle:** Throw.cpp

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
