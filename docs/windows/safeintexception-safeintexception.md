---
title: 'SafeIntException:: SafeIntException | Microsoft-Dokumentation'
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
ms.openlocfilehash: 744bf034572745cd88a35f47a1ca2da03e900fd8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606656"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException
Erstellt eine **SafeIntException** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Code*  
 Ein Aufzählungsdaten-Wert, der den Fehler beschreibt, der aufgetreten sind.  
  
## <a name="remarks"></a>Hinweise  
 Die möglichen Werte für *Code* werden in der Datei Safeint.h definiert. Der Einfachheit halber sind die möglichen Werte auch hier aufgeführt.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** MSL:: Utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeIntException-Klasse](../windows/safeintexception-class.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)