---
title: _bstr_t::GetBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetBSTR
dev_langs: C++
helpviewer_keywords: GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00b2f7f487673c67aa7b681499462ea05a471b48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft-spezifisch**  
  
 Zeigt auf den Anfang des `BSTR`, das vom `_bstr_t` umschlossen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der Anfang des `BSTR`, der vom `_bstr_t` umschlossen ist.  
  
## <a name="remarks"></a>Hinweise  
 `GetBSTR` wirkt sich auf alle `_bstr_t`-Objekte aus, die ein `BSTR` freigeben. Mehr als eine `_bstr_t` kann eine `BSTR` durch die Verwendung des Kopierkonstruktors und des `operator=` freigeben.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel mit `GetBSTR`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)