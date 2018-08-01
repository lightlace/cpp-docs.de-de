---
title: _bstr_t::Attach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f69811b7b25a793d11ef6d53aaf0638c752a11
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409105"
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft-spezifisch**  
  
 Verknüpft einen `_bstr_t`-Wrapper mit einem `BSTR`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *s*  
 Eine `BSTR`-Variable, die `_bstr_t` zugeordnet oder zugewiesen werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `_bstr_t` zuvor an einen anderen `BSTR` angefügt war, bereinigt `_bstr_t` die `BSTR`-Ressource, wenn keine anderen `_bstr_t`-Variablen den `BSTR` verwenden.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein Beispiel mit **Anfügen**.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)