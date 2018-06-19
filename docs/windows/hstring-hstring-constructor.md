---
title: 'Hstring:: Hstring-Konstruktor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3188e137d3a39fb26ca4151f72073306038e46f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876877"
---
# <a name="hstringhstring-constructor"></a>HString::HString-Konstruktor
Initialisiert eine neue Instanz der HString-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `hstr`  
 Ein HSTRING-Handle.  
  
 `other`  
 Ein vorhandenes HString-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert ein neues HString-Objekt, das leer ist.  
  
 Der zweite Konstruktor initialisiert ein neues HString-Objekt, auf den Wert des vorhandenen `other` Parameter, und klicken Sie dann zerstört die `other` Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)