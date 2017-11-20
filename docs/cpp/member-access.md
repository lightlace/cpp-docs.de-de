---
title: Memberzugriff | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 03a382191e78780aa350741b9cfceac11305cdcb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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