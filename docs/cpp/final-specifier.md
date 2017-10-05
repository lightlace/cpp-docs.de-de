---
title: final-Bezeichner | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- final
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
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
ms.openlocfilehash: c9f0a638707466778e75a3eabfe838c84b0355d7
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="final-specifier"></a>final-Bezeichner
Verwenden Sie das `final`-Schlüsselwort, um virtuelle Funktionen festzulegen, die in einer abgeleiteten Klasse nicht überschreibbar sind. Sie können es auch verwenden, um Klassen festzulegen, die nicht vererbbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Hinweise  
 `final` ist kontextbezogen und hat nur dann eine besondere Bedeutung, wenn es nach der Deklaration einer Funktion oder eines Klassennamens verwendet wird; andernfalls ist es kein reserviertes Schlüsselwort.  
  
 Wenn `final` in den Klassendeklarationen verwendet wird, ist `base-classes` ein optionaler Teil der Deklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das `final`-Schlüsselwort verwendet, um anzugeben, dass eine virtuelle Funktion nicht überschrieben werden kann.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 Informationen zum angeben, dass Memberfunktionen außer Kraft gesetzt werden können, finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md).  
  
 Im folgenden Beispiel wird das `final`-Schlüsselwort verwendet, um anzugeben, dass eine Klasse nicht vererbt werden kann.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [override-Bezeichner](../cpp/override-specifier.md)
