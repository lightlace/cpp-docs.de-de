---
title: "Windows-Runtime und verwaltete Vorlagen (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81e803db04ebd9d3a851a04e8656131d85649751
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-runtime-and-managed-templates-c-component-extensions"></a>Windows-Laufzeit und verwaltete Vorlagen (Komponentenerweiterungen für C++)
Vorlagen ermöglichen es Ihnen, einen Prototyp eines Windows-Runtime oder der common Language Runtime-Typ definieren und dann mithilfe von verschiedenen Vorlagentypparameter instanziieren Variationen dieses Typs.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Sie können Vorlagen von Werttypen oder Referenztypen erstellen.  Weitere Informationen zum Erstellen von Werttypen oder Referenztypen, finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Weitere Informationen zu Standard-c++-Klassenvorlagen, finden Sie unter [Klassenvorlagen](../cpp/class-templates.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Es gibt einige Einschränkungen für das Erstellen von Klassenvorlagen von verwalteten Typen, bei denen in den folgenden Codebeispielen dargestellt werden.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Es ist möglich, beim Instanziieren eines generischen Typs mit einem verwalteten Typ Template-Parameter, aber eine verwaltete Vorlage mit einem generischen Typparameter für die Vorlage kann nicht instanziiert werden.  Dies liegt daran generische Typen zur Laufzeit aufgelöst werden.  Weitere Informationen finden Sie unter [Generika und Vorlagen (Visual C++)](../windows/generics-and-templates-visual-cpp.md).  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **Beispiel**  
  
 Ein generischer Typ oder die Funktion kann nicht in einer verwalteten Vorlage geschachtelt werden.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **Beispiel**  
  
 Kann nicht auf Vorlagen definiert, die in einer referenzierten Assembly C + c++ / CLI-Sprachsyntax, aber Sie können mithilfe von Reflektion.  Wenn eine Vorlage nicht instanziiert wird, wird er nicht in den Metadaten ausgegeben.  Wenn eine Vorlage instanziiert wird, werden nur auf die verwiesen wird Memberfunktionen in den Metadaten angezeigt.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **Beispiel**  
  
 Sie können die verwalteten Modifizierer einer Klasse in eine teilweise Spezialisierung oder explizite Spezialisierung einer Klassenvorlage ändern.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)