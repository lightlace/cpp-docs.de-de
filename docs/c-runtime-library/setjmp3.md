---
title: _setjmp3 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _setjmp3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- setjmp3
- _setjmp3
dev_langs:
- C++
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04d06bd7728347770bd17c48abc9898f2a2467a4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="setjmp3"></a>_setjmp3
Interne CRT-Funktion. Eine neue Implementierung der Funktion `setjmp`.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _setjmp3(  
   OUT jmp_buf env,  
   int count,  
   (optional parameters)  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `env`  
 Adresse des Puffers zur Speicherung von Statusinformationen.  
  
 [in] `count`  
 Die Anzahl zusätzlicher `DWORD`s von Informationen, die in der `optional parameters` gespeichert werden.  
  
 [in] `optional parameters`  
 Zusätzliche vom systeminternen Objekt `setjmp` nach unten geschobene Daten. Das erste `DWORD` ist ein Funktionszeiger, der verwendet wird, um zusätzliche Daten aufzurufen und zu einem nichtflüchtigen Speicherstatus zurückzukehren. Das zweite `DWORD` ist die wiederherzustellende Versuchsebene. Alle weiteren Daten werden im generischen Datenarray im `jmp_buf` gespeichert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion nicht in einem C++-Programm. Es handelt sich um eine intrinsische Funktion, die C++ nicht unterstützt. Weitere Informationen zum Verwenden von `setjmp` finden Sie unter [Verwenden von „setjmp/longjmp“](../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetical Function Reference (Alphabetische Funktionsreferenz)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [setjmp](../c-runtime-library/reference/setjmp.md)