---
title: ComPtr::Reset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad9dd8bc8c180d8a1fd7bf90965349c620eab54b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrreset"></a>ComPtr::Reset
Gibt alle Verweise für den Zeiger auf die Schnittstelle an, die diesem ComPtr zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl der freigegeben Verweise, sofern vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ComPtr-Klasse](../windows/comptr-class.md)