---
title: 'Hstring:: Hstring-Konstruktor | Microsoft-Dokumentation'
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
ms.openlocfilehash: 96b77ec87e3219206d353f56293fc201c46f5d7e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568770"
---
# <a name="hstringhstring-constructor"></a>HString::HString-Konstruktor
Initialisiert eine neue Instanz der dem **HString** Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *HSTR*  
 Ein HSTRING-Handle.  
  
 *other*  
 Eine vorhandene **HString** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert eine neue **HString** -Objekt, das leer ist.  
  
 Der zweite Konstruktor initialisiert eine neue **HString** Objekt, das den Wert des vorhandenen *andere* Parameter, und klicken Sie dann zerstört die *andere* Parameter.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [HString-Klasse](../windows/hstring-class.md)