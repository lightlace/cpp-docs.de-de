---
title: once_flag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: mutex/std::once_flag
dev_langs: C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc66f322490bc728ab6d25e185f6b8d4ce0f0179
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="onceflag-structure"></a>once_flag-Struktur
Stellt eine `struct` dar, die mit der Vorlagenfunktion [call_once](../standard-library/mutex-functions.md#call_once) verwendet wird, damit der Initialisierungscode auch bei mehreren Ausführungsthreads nur einmal aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
Struktur once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>Hinweise  
 Die `once_flag` `struct` verfügt über nur einen Standardkonstruktor.  
  
 Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Mutex >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



