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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: bba7b35c08fbc171ddbb4c572285c0aed2f58a3b
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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

 Darüber hinaus, in Visual Studio .NET 2003 und höher können Membervorlagen auch außerhalb einer Klasse definiert werden.  
  
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
  
 Visual C++ .NET 2003 wurde die Unterstützung für auf Vorlagen basierende benutzerdefinierte Konvertierungen eingeführt. Das folgende Beispiel funktioniert in Visual C++ .NET 2003 wie im Standard angegeben.  
  
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

