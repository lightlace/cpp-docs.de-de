---
title: _initterm, _initterm_e | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _initterm_e
- _initterm
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs: C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 95f508b1198cd009abe0cf82cbe9a7aaf553240f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e
Interne Methoden, die eine Tabelle von Funktionszeigern durchlaufen und sie initialisieren.  
  
 Der erste Zeiger ist die Anfangsposition in der Tabelle, und der zweite Zeiger ist die Endposition.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Fehlercode ungleich null, wenn eine Initialisierung fehlschlägt und einen Fehler auslöst; 0, wenn kein Fehler auftritt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methoden werden während der Initialisierung eines C++-Programms nur intern aufgerufen. Rufen Sie diese Methoden nicht in einem Programm auf.  
  
 Wenn diese Methoden eine Tabelle mit Funktionseinträgen durchlaufen, überspringen sie `NULL`-Einträge und fahren fort.  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)