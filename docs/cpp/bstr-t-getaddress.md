---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1b2b348277f7d33a32c8d0e6ad1fc80d51ec68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft-spezifisch**  
  
 Setzt etwaig vorhandene Zeichenfolgen frei und gibt die Adresse einer neu zugeordneten Zeichenfolge zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den `BSTR` umschlossen von `_bstr_t`.  
  
## <a name="remarks"></a>Hinweise  
 `GetAddress` wirkt sich auf alle `_bstr_t`-Objekte aus, die ein `BSTR` freigeben. Mehr als eine `_bstr_t` kann eine `BSTR` durch die Verwendung des Kopierkonstruktors und des `operator=` freigeben.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) für eine Beispiel-mit `GetAddress`.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)