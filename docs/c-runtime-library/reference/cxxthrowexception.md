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
ms.openlocfilehash: bd3ab2994359e99e490422fbb2f11cf28a05d6e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395659"
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

*pExceptionObject* das Objekt, das die Ausnahme generiert hat.

*pThrowInfo* die Informationen, die erforderlich ist, um die Ausnahme zu verarbeiten.

## <a name="remarks"></a>Hinweise

Diese Methode ist in einer compilerspezifischen Datei enthalten, die vom Compiler zum Verarbeiten von Ausnahmen verwendet wird. Rufen Sie die Methode nicht direkt aus Ihrem Code auf.

## <a name="requirements"></a>Anforderungen

**Quelle:** Throw.cpp

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
