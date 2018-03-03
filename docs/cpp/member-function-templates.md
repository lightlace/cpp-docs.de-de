---
title: Memberfunktionsvorlagen | Microsoft Docs
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
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6d16c94eb9d88f8e000f3830477fbf420acf8b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="member-function-templates"></a>Memberfunktionsvorlagen

Der Ausdruck "Membervorlage" bezieht sich auf Memberfunktionsvorlagen und geschachtelte Klassenvorlagen. Memberfunktionsvorlagen sind Vorlagenfunktionen, die Member einer Klasse oder einer Klassenvorlage sind.  
  
 Memberfunktionen können in mehreren Kontexten Funktionsvorlagen sein. Alle Funktionen von Klassenvorlagen sind generisch, werden jedoch nicht als Membervorlagen oder Memberfunktionsvorlagen bezeichnet. Wenn diese Memberfunktionen eigene Vorlagenargumente übernehmen, werden sie als Memberfunktionsvorlagen betrachtet.  
  
## <a name="example"></a>Beispiel

 Memberfunktionsvorlagen von nicht auf Vorlagen basierenden Klassen oder Vorlagenklassen werden als Funktionsvorlagen mit ihren Vorlagenparametern deklariert.  
  
```cpp
// member_function_templates.cpp  
struct X  
{  
   template <class T> void mf(T* t) {}  
};  
  
int main()  
{  
   int i;  
   X* x = new X();  
   x->mf(&i);  
}  
```  
  
## <a name="example"></a>Beispiel

 Das folgende Beispiel zeigt eine Memberfunktionsvorlage einer Vorlagenklasse.  
  
```cpp
// member_function_templates2.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u)  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Beispiel
  
```cpp
// defining_member_templates_outside_class.cpp  
template<typename T>  
class X  
{  
public:  
   template<typename U>  
   void mf(const U &u);  
};  
  
template<typename T> template <typename U>  
void X<T>::mf(const U &u)  
{  
}  
  
int main()  
{  
}  
```  
  
## <a name="example"></a>Beispiel

 Lokale Klassen dürfen keine Membervorlagen haben.  
  
 Membervorlagenfunktionen können keine virtuellen Funktionen sein und können keine virtuellen Funktionen einer Basisklasse überschreiben, wenn sie mit dem gleichen Namen wie eine virtuelle Funktion der Basisklasse deklariert werden.  
  
Das folgende Beispiel zeigt eine auf Vorlagen basierende benutzerdefinierte Konvertierung:  
  
```cpp
// templated_user_defined_conversions.cpp  
template <class T>  
struct S  
{  
   template <class U> operator S<U>()  
   {  
      return S<U>();  
   }  
};  
  
int main()  
{  
   S<int> s1;  
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.  
}  
```  
  
## <a name="see-also"></a>Siehe auch

 [Funktionsvorlagen](../cpp/function-templates.md)
