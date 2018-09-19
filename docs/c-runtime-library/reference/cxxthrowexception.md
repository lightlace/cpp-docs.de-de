---
title: _CxxThrowException | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7adf4c285646e6a3f4706a9a56995f4440cc1e8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103814"
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
