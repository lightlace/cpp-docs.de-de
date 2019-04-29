---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: 19eabc3b5a11246d5b0056bdafbb169e2a7de9f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332194"
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable

Übernimmt oder bestimmt ein Flag, das angibt, ob die Gleitkomma Transzendente Math-Bibliotheksfunktionen FMA3-Anweisungen im kompilierten Code für X64 verwenden Plattformen.

## <a name="syntax"></a>Syntax

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Parameter

*flag*<br/>
Auf 1 festgelegt ist, aktivieren Sie die FMA3-Implementierungen, der das Gleitkomma Transzendente Math-Bibliotheksfunktionen auf X64 Plattformen, oder 0, um die Implementierungen zu verwenden, die keine FMA3-Anweisungen verwenden.

## <a name="return-value"></a>Rückgabewert

Ein Wert ungleich NULL, wenn die FMA3-Implementierungen, der das Gleitkomma Transzendente Math-Bibliotheksfunktionen aktiviert sind. Andernfalls 0 (null).

## <a name="remarks"></a>Hinweise

Verwenden Sie die **_set_FMA3_enable** Funktion zu aktivieren oder deaktivieren Sie die Verwendung von FMA3-Anweisungen in die Transzendente mathematische Gleitkommafunktionen in der CRT-Bibliothek. Der Rückgabewert gibt die Implementierung verwendet, nach der Änderung wieder. Wenn die CPU FMA3-Anweisungen nicht unterstützt, diese Funktion nicht aktivieren, in der Bibliothek und der Rückgabewert ist 0 (null). Verwendung **_get_FMA3_enable** auf den aktuellen Status der Bibliothek abzurufen. Standardmäßig auf X64 Plattformen, die die CRT-Startcode erkennt, ob die CPU FMA3-Anweisungen unterstützt und aktiviert oder die FMA3-Implementierungen in der Bibliothek deaktiviert.

Da die FMA3-Implementierungen verschiedene Algorithmen verwenden, möglicherweise geringfügige Unterschiede in das Ergebnis von Berechnungen Observable-Objekt, wenn die FMA3-Implementierungen aktiviert oder deaktiviert sind, oder zwischen Computern, die oder FMA3 nicht unterstützt. Weitere Informationen finden Sie unter [Gleitkomma-Migrationsprobleme](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Anforderungen

Die **_set_FMA3_enable** und **_get_FMA3_enable** Funktionen sind nur verfügbar, in der X64 CRT-Versionen.

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_FMA3_enable**, **_get_FMA3_enable**| C: \<math.h><br />C++: \<Cmath > oder \<math.h >|

Die **_set_FMA3_enable** und **_get_FMA3_enable** Funktionen sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Gleitkomma-Migrationsprobleme](../../porting/floating-point-migration-issues.md)<br/>
