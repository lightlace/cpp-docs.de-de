---
title: _bstr_t::Copy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d23f204e7e8a545fbee7ab516495ed711d7984a9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943687"
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft-spezifisch**  
  
 Erstellt eine Kopie des gekapselten `BSTR`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
BSTR copy( bool fCopy = true ) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 *fCopy*  
 True gibt an, `copy` gibt eine Kopie des enthaltenen `BSTR`, andernfalls `copy` den tatsächlichen BSTR zurück.  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine neu zugeordnete Kopie des gekapselten `BSTR`-Objekts zurück.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)