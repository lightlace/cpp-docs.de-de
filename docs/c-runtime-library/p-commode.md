---
title: __p__commode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: cdb058b0173e15d17f47a90d6101aca65954c814
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="pcommode"></a>__p__commode
Verweist auf die globale Variable `_commode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf die globale Variable `_commode`.  
  
## <a name="remarks"></a>Hinweise  
 Die `__p__commode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.  
  
 Der Datei-Commit-Modus gibt an, wenn wichtige Daten auf den Datenträger geschrieben werden. Weitere Informationen finden Sie unter [fflush](../c-runtime-library/reference/fflush.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|__p\__commode|internal.h|
