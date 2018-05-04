---
title: Änderbare Datenmember (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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