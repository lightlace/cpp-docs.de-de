---
title: _bstr_t::GetAddress | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaa3921d0f1f89df11cf5e3809c9e90e4a03dd3b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408465"
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
 **GetAddress** wirkt sich auf alle `_bstr_t` Objekte die Freigabe einer `BSTR`. Mehr als eine `_bstr_t` können Freigeben einer `BSTR` durch die Verwendung des Kopierkonstruktors und und **Operator =**.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein mit **GetAddress**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)