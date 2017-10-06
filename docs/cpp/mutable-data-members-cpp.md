---
title: "Änderbare Datenmember (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
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
ms.openlocfilehash: b51f53444b7482575398b68c3a2bf52b3de96e55
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="mutable-data-members-c"></a>Änderbare Datenmember (C++)
Dieses Schlüsselwort kann nur auf nicht statische und nicht konstante Datenmember einer Klasse angewendet werden. Wenn ein Datenmember deklariert wird `mutable`, ist es zulässig, die dieses Datenelement aus einen Wert zuweisen einer **const** Memberfunktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Hinweise  
 Beispielsweise wird der folgende Code ohne Fehler kompiliert, da `m_accessCount` als `mutable` deklariert wurde und daher von `GetFlag` geändert werden kann, obwohl `GetFlag` eine const-Memberfunktion ist.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
