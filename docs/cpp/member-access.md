---
title: Memberzugriff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators
- pointers, smart
- member access, overloaded operators
- operator overloading, member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 21cdc3de990a8b23645bb09f9f093fb0f2498254
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="member-access"></a>Memberzugriff
Klassenmemberzugriff kann gesteuert werden, indem der Memberzugriffsoperator überladen (**->**). Dieser Operator wird bei dieser Verwendung als unärer Operator betrachtet, und die überladene Operatorfunktion muss eine Klassenmemberfunktion sein. Daher ist die Deklaration für eine solche Funktion:  
  
## <a name="syntax"></a>Syntax  
  
```  
  
class-type *operator->()  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei *Klassentyp* ist der Name der Klasse, zu der dieser Operator gehört. Die Operatorfunktion für den Memberzugriff muss eine nicht statische Memberfunktion sein.  
  
 Dieser Operator wird (oft in Verbindung mit dem Zeiger-Dereferenzierungsoperator) verwendet, um "intelligente Zeiger" zu implementieren, die vor einer Dereferenzierung oder Zählung validiert werden.  
  
 Das Sprachelement **.** Memberzugriffsoperator kann nicht überladen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)
