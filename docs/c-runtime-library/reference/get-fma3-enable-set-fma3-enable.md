---
title: _get_FMA3_enable _set_FMA3_enable | Microsoft Docs
ms.custom: 
ms.date: 6/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4875306575d58b1baf341a5ed3c2a919c995c704
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable, _set_FMA3_enable
Ruft ab oder legt ein Flag, das angibt, ob die Gleitkomma Transzendente Math-Bibliotheksfunktionen FMA3 Anweisungen im kompilierten Code für X64 verwenden Plattformen.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```  
  
### <a name="parameters"></a>Parameter
*flag*  
Auf 1 festgelegt wird, um die FMA3 Implementierungen der Gleitkomma Transzendente Math-Bibliotheksfunktionen auf X64 aktivieren-Plattformen oder auf 0, um die Implementierungen verwenden, die keine FMA3-Anweisungen verwenden.
  
## <a name="return-value"></a>Rückgabewert  
Ein Wert ungleich NULL, wenn die FMA3 Implementierungen der Gleitkomma Transzendente Math-Bibliotheksfunktionen aktiviert sind. Andernfalls 0 (null).  
  
## <a name="remarks"></a>Hinweise  
Verwenden Sie die `_set_FMA3_enable` Funktion aktivieren oder deaktivieren die Verwendung von FMA3-Anweisungen in der Transzendente mathematische Gleitkommafunktionen in der CRT-Bibliothek. Der Rückgabewert gibt die Implementierung verwendet nach der Änderung wieder. Wenn die CPU-Nutzung FMA3 Anweisungen nicht unterstützt, diese Funktion kann nicht in der Bibliothek aktivieren und der Rückgabewert ist 0 (null). Verwendung `_get_FMA3_enable` auf den aktuellen Status der Bibliothek abzurufen. Wird standardmäßig auf X64-Plattformen die CRT-Startcode erkennt, ob die CPU-Nutzung FMA3-Anweisungen unterstützt und aktiviert oder die FMA3-Implementierungen in der Bibliothek deaktiviert.
  
Da FMA3 Implementierungen verschiedene Algorithmen verwendet werden, möglicherweise geringfügige unterschieden dahingehend, das Ergebnis von Berechnungen Observable-Objekt, wenn Implementierungen der FMA3 aktiviert oder deaktiviert sind, oder zwischen Computern, die oder FMA3 nicht unterstützt. Weitere Informationen finden Sie unter [Gleitkomma Migrationsprobleme](../../porting/floating-point-migration-issues.md).

## <a name="requirements"></a>Anforderungen  
  
Die `_set_FMA3_enable` und `_get_FMA3_enable` Funktionen stehen nur in der X64 CRT-Versionen.  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_set_FMA3_enable` <br /><br /> `_get_FMA3_enable`| C: \<math.h><br /><br /> C++: \<Cmath > oder \<math.h >|  
  
Die Funktionen `_set_FMA3_enable` und `_get_FMA3_enable` sind Microsoft-spezifisch. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)
[Gleitkomma Migrationsprobleme](../../porting/floating-point-migration-issues.md)  