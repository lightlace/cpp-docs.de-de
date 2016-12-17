---
title: "&#196;nderbare Datenmember (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "mutable_cpp"
  - "mutable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mutable-Schlüsselwort [C++]"
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# &#196;nderbare Datenmember (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Schlüsselwort kann nur auf nicht statische und nicht konstante Datenmember einer Klasse angewendet werden.  Wenn ein Datenmember als `mutable` deklariert wird, ist es zulässig, seinem Datenmember einen Wert aus einer **const**\-Memberfunktion zuzuweisen.  
  
## Syntax  
  
```  
  
mutable member-variable-declaration;  
```  
  
## Hinweise  
 Beispielsweise wird der folgende Code ohne Fehler kompiliert, da `m_accessCount` als `mutable` deklariert wurde und daher von `GetFlag` geändert werden kann, obwohl `GetFlag` eine const\-Memberfunktion ist.  
  
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
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)