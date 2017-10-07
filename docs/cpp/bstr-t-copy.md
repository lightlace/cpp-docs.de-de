---
title: _bstr_t::Copy | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 25167305ae817ebd9d979c0145934996bbbfcddc
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft-spezifisch**  
  
 Erstellt eine Kopie des gekapselten `BSTR`.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 `fCopy`  
 Wenn **"true"**, **Kopie** gibt eine Kopie des enthaltenden `BSTR`, da andernfalls **Kopie** den tatsächlichen BSTR zurück.  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine neu zugeordnete Kopie des gekapselten `BSTR`-Objekts zurück.  
  
## <a name="example"></a>Beispiel  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)
