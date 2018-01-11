---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs: C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cbfe1f002c038f5dcc1b3a024891780d56c3572c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool
Stellt eine implizite Konvertierung von `vector<bool>::reference` in `bool` bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator bool() const;
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der boolesche Wert des Elements des [vector\<bool>](../standard-library/vector-bool-class.md)-Objekts.  
  
## <a name="remarks"></a>Hinweise  
 Das `vector<bool>`-Objekt kann von diesem Operator nicht geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<vector>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [vector\<bool>::reference-Klasse](../standard-library/vector-bool-reference-class.md)   
 [C++ Standard Library Reference (C++-Standardbibliotheksreferenz)](../standard-library/cpp-standard-library-reference.md)

