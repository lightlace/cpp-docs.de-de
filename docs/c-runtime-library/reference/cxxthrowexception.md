---
title: _CxxThrowException | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5cfe894dc20e77bf34067c16fddd74432c522bda
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="cxxthrowexception"></a>_CxxThrowException
Erstellt den Ausnahmedatensatz und ruft die Laufzeitumgebung auf, um die Verarbeitung der Ausnahme zu starten.  
  
## <a name="syntax"></a>Syntax  
  
```  
extern "C" void __stdcall _CxxThrowException(  
   void* pExceptionObject  
   _ThrowInfo* pThrowInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `pExceptionObject`  
 Das Objekt, durch das die Ausnahme erzeugt wurde.  
  
 [in] `pThrowInfo`  
 Die zum Verarbeiten der Ausnahme erforderlichen Informationen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist in einer compilerspezifischen Datei enthalten, die vom Compiler zum Verarbeiten von Ausnahmen verwendet wird. Rufen Sie die Methode nicht direkt aus Ihrem Code auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Quelle:** Throw.cpp  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)
