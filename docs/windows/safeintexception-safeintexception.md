---
title: 'SafeIntException:: SafeIntException | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85bf6bae5ba07154bdeb807171dd2d3df61d0774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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