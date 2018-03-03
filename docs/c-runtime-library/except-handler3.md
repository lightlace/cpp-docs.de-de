---
title: _except_handler3 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4fe280562d4f1278d74ae118712c9167de4b54d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="excepthandler3"></a>_except_handler3
Interne CRT-Funktion. Wird von einem Framework verwendet, um den passenden Ausnahmehandler zur Verarbeitung der aktuellen Ausnahme zu suchen.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `exception_record`  
 Informationen über die spezifische Ausnahme.  
  
 [in] `registration`  
 Die Aufzeichnung, die anzeigt, welche Bereichstabelle für die Suche nach dem Ausnahmehandler verwendet werden soll.  
  
 [in] `context`  
 Reserviert.  
  
 [in] `dispatcher`  
 Reserviert.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `DISPOSITION_DISMISS` zurück, wenn eine Ausnahme verworfen wird. Gibt `DISPOSITION_CONTINUE_SEARCH` zurück, wenn die Ausnahme eine Ebene höher an die kapselnden Ausnahmehandler übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn diese Methode einen passenden Ausnahmehandler findet, übergibt sie die Ausnahme an diesen Handler. In dieser Situation wird diese Methode nicht an den Code zurückgegeben, der sie aufgerufen hat, und der Rückgabewert ist irrelevant.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../c-runtime-library/reference/crt-alphabetical-function-reference.md)