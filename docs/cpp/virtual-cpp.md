---
title: virtuelle (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs:
- C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 851f911dd7c49df1d685afe63ef5134cf0d5f175
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="virtual-c"></a>virtual (C++)
Das `virtual`-Schlüsselwort deklariert eine virtuelle Funktion oder eine virtuelle Basisklasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>Parameter  
 `type-specifiers`  
 Gibt den Rückgabetyp der virtuellen Memberfunktion an.  
  
 `member-function-declarator`  
 Deklariert eine Memberfunktion.  
  
 `access-specifier`  
 Definiert die Ebene des Zugriffs auf die Basisklasse, `public`, `protected` oder `private`. Kann vor oder nach dem `virtual`-Schlüsselwort angezeigt werden.  
  
 `base-class-name`  
 Identifiziert einen zuvor deklarierten Klassentyp.  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [virtuelle Funktionen](../cpp/virtual-functions.md) für Weitere Informationen.  
  
 Siehe auch die folgenden Schlüsselwörter: [Klasse](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [öffentlichen](../cpp/public-cpp.md), und [geschützt](../cpp/protected-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
