---
title: "final-Bezeichner"
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
  - "final"
  - "final_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "final-Bezeichner"
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# final-Bezeichner
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie das `final`\-Schlüsselwort, um virtuelle Funktionen festzulegen, die in einer abgeleiteten Klasse nicht überschreibbar sind.  Sie können es auch verwenden, um Klassen festzulegen, die nicht vererbbar sind.  
  
## Syntax  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## Hinweise  
 `final` ist kontextbezogen und hat nur dann eine besondere Bedeutung, wenn es nach der Deklaration einer Funktion oder eines Klassennamens verwendet wird; andernfalls ist es kein reserviertes Schlüsselwort.  
  
 Wenn `final` in den Klassendeklarationen verwendet wird, ist `base-classes` ein optionaler Teil der Deklaration.  
  
## Beispiel  
 Im folgenden Beispiel wird das `final`\-Schlüsselwort verwendet, um anzugeben, dass eine virtuelle Funktion nicht überschrieben werden kann.  
  
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
  
 Informationen dazu, wie Sie angeben, dass Memberfunktionen überschrieben werden können, finden Sie unter [override\-Bezeichner](../cpp/override-specifier.md).  
  
 Im folgenden Beispiel wird das `final`\-Schlüsselwort verwendet, um anzugeben, dass eine Klasse nicht vererbt werden kann.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](assetId:///b53ba470-e583-4e5c-b634-6018f6110674)   
 [override\-Bezeichner](../cpp/override-specifier.md)