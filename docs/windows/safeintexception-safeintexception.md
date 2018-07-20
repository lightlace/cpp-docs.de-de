---
title: 'SafeIntException:: SafeIntException | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ef3c1d11c0f814699ca1492f7ec1fb49c43c3d76
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892175"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException
Erstellt ein `SafeIntException`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `code`  
 Eine aufgelistete Datenwert, der den Fehler beschreibt, der aufgetreten sind.  
  
## <a name="remarks"></a>Hinweise  
 Die möglichen Werte für `code` sind in der Datei Safeint.h definiert. Der Einfachheit halber werden die möglichen Werte hier ebenfalls aufgeführt.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeIntException-Klasse](../windows/safeintexception-class.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)