---
title: final-Bezeichner | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82fb9e13fc5dbbafcc37905716a37322b2966c6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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