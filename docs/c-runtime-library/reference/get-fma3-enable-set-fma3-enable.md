---
title: _get_FMA3_enable, _set_FMA3_enable
ms.date: 04/05/2018
api_name:
- _get_FMA3_enable
- _set_FMA3_enable
api_location:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
ms.openlocfilehash: dee75bf5b16b5fe5b619444f7f2736010bb42a84
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857808"
---
# <a name="_get_fma3_enable-_set_fma3_enable"></a>_get_FMA3_enable, _set_FMA3_enable

Ruft ein Flag ab, das angibt, ob die Funktionen der transendental-Gleit Komma Bibliothek FMA3 im für x64-Plattformen kompilierten Code verwenden, oder legt dieses fest.

## <a name="syntax"></a>Syntax

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>Parameters

*flag*<br/>
Legen Sie den Wert auf 1 fest, um die FMA3-Implementierungen der Funktionen der transendental-Gleit Komma Bibliothek auf x64-Plattformen zu aktivieren, oder auf 0, um die Implementierungen zu verwenden, die keine FMA3-Anweisungen verwenden.

## <a name="return-value"></a>Rückgabewert

Ein Wert ungleich 0 (null), wenn die FMA3-Implementierungen der Funktionen der transendental-Gleit Komma Bibliothek aktiviert sind. Andernfalls 0 (null).

## <a name="remarks"></a>Hinweise

Verwenden Sie die **_set_FMA3_enable** -Funktion, um die Verwendung von FMA3-Anweisungen in den transendental-mathematischen Gleit Komma Funktionen in der CRT-Bibliothek zu aktivieren oder zu deaktivieren. Der Rückgabewert gibt die-Implementierung an, die nach der Änderung verwendet wird. Wenn die CPU FMA3-Anweisungen nicht unterstützt, kann diese Funktion Sie nicht in der Bibliothek aktivieren, und der Rückgabewert ist 0 (null). Verwenden Sie **_get_FMA3_enable** , um den aktuellen Status der Bibliothek zu erhalten. Standardmäßig erkennt der CRT-Startcode auf x64-Plattformen, ob die CPU FMA3-Anweisungen unterstützt, und aktiviert oder deaktiviert die FMA3-Implementierungen in der Bibliothek.

Da die FMA3-Implementierungen verschiedene Algorithmen verwenden, sind geringfügige Unterschiede im Ergebnis von Berechnungen möglicherweise Observable, wenn die FMA3-Implementierungen aktiviert oder deaktiviert werden, oder zwischen Computern, die FMA3 unterstützen oder nicht unterstützen. Weitere Informationen finden Sie unter [Probleme](../../porting/floating-point-migration-issues.md)bei der Migration von Gleit Komma Werten.

## <a name="requirements"></a>-Anforderungen

Die Funktionen **_set_FMA3_enable** und **_get_FMA3_enable** sind nur in den x64-Versionen der CRT verfügbar.

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_FMA3_enable** **_get_FMA3_enable**| C: \<math.h><br />C++: \<cmath-> oder \<Math. h->|

Die Funktionen **_set_FMA3_enable** und **_get_FMA3_enable** sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleit Komma Unterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Gleitkomma-Migrationsprobleme](../../porting/floating-point-migration-issues.md)<br/>
