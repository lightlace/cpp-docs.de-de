---
title: __p__fmode | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __p__fmode
apilocation:
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords: __p__fmode
dev_langs: C++
helpviewer_keywords: __p__fmode
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 341eab038db17b39e5b2a408db7c61c69d432fe9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pfmode"></a>__p__fmode
Verweist auf die globale Variable `_fmode`, die den Standard *Datei-Commit-Modus* für E/A-Dateivorgänge angibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Zeiger auf die globale Variable `_fmode`.  
  
## <a name="remarks"></a>Hinweise  
 Die `__p__fmode`-Funktion steht nur für die interne Verwendung zur Verfügung und sollte nicht vom Benutzercode aufgerufen werden.  
  
 Der Dateiübersetzungsmodus gibt entweder `binary`- oder `text`-Übersetzungen für [_open](../c-runtime-library/reference/open-wopen.md)- und [_pipe](../c-runtime-library/reference/pipe.md)-E/A-Vorgänge an. Weitere Informationen finden Sie unter [_fmode](../c-runtime-library/fmode.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|__p\__fmode|stdlib.h|