---
title: Typname | Microsoft Docs
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
ms.openlocfilehash: b6eebf038fbe3e5e18e3f2a1e8e7a2aa2554bf41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="typename"></a>typename
In den Vorlagendefinitionen bietet einem Hinweis für den Compiler an, dass ein Unbekannter Bezeichner ein Typ ist. In Vorlagenparameterlisten verwendet, um einen Typparameter anzugeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Schlüsselwort muss verwendet werden, wenn ein Name in eine Vorlagendefinition ein qualifizierter Name ist, der von einem Vorlagenargument abhängig ist. Es ist optional, wenn der qualifizierte Name nicht abhängig ist. Weitere Informationen finden Sie unter [Vorlagen und namensauflösung](../cpp/templates-and-name-resolution.md).  
  
 **TypeName** können von jedem Typ an einer beliebigen Stelle in einer Vorlagendeklaration oder-Definition verwendet werden. Es ist in der Basisklassenliste nicht zulässig, außer als Vorlagenargument für eine Vorlagenbasisklasse.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 Die **Typename** -Schlüsselwort kann auch verwendet werden, anstelle von **Klasse** führt in der Template-Parameter. Beispielsweise sind die folgenden Anweisungen semantisch gleichwertig:  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>Beispiel  
  
```  
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