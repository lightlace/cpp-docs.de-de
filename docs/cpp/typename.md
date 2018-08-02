---
title: TypeName | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79ba7d0bda73762d04f0dd11668eb31c275ac03f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467928"
---
# <a name="typename"></a>typename
In den Vorlagendefinitionen enthält einem Hinweis für den Compiler an, dass ein Unbekannter Bezeichner ein Typ ist. In Vorlagenparameterlisten verwendet, um einen Typparameter anzugeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typename identifier;  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Schlüsselwort muss verwendet werden, wenn Sie ein Namen im eine Vorlagendefinition ein qualifizierter Name ist, der von einem Vorlagenargument abhängig ist; Dies ist optional, wenn der qualifizierte Name nicht abhängig ist. Weitere Informationen finden Sie unter [Vorlagen und namensauflösung](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** kann von jedem Typ an einer beliebigen Stelle in einer Vorlagendeklaration oder-Definition verwendet werden. Es ist in der Basisklassenliste nicht zulässig, außer als Vorlagenargument für eine Vorlagenbasisklasse.  
  
```cpp 
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 Die **Typename** -Schlüsselwort kann auch verwendet werden, anstelle von **Klasse** Vorlagenparameterlisten. Die folgenden Anweisungen sind z. B. semantisch gleichwertig:  
  
```cpp 
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Beispiel  
  
```cpp 
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorlagen](../cpp/templates-cpp.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)