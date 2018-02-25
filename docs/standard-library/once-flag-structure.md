---
title: once_flag-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 482ef221338651ef3e6f6ec272c1a48984d40912
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="onceflag-structure"></a>once_flag-Struktur
Stellt eine `struct` dar, die mit der Vorlagenfunktion [call_once](../standard-library/mutex-functions.md#call_once) verwendet wird, damit der Initialisierungscode auch bei mehreren Ausführungsthreads nur einmal aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
Struktur once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>Hinweise  
 Die `once_flag` `struct` verfügt über nur einen Standardkonstruktor.  
  
 Objekte vom Typ `once_flag` können erstellt, aber nicht kopiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<mutex>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



