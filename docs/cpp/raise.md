---
title: __raise | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs: C++
helpviewer_keywords: __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a84673379f89a20d198fdac4d97185182a3a05c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="raise"></a>__raise
Hebt die Aufrufsite eines Ereignisses hervor.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Aus verwaltetem Code kann ein Ereignis nur innerhalb der Klasse ausgelöst werden, in der es definiert ist. Finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md) für Weitere Informationen.  
  
 Das Schlüsselwort `__raise` bewirkt die Ausgabe eines Fehlers bei einem nicht ereignisgebundenen Aufruf.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## <a name="example"></a>Beispiel  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Ereignisbehandlung](../cpp/event-handling.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)