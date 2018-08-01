---
title: final-Bezeichner | Microsoft-Dokumentation
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
ms.openlocfilehash: f28ae7b7cb8bdcf335757c58d5e744974f4c7cad
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405956"
---
# <a name="final-specifier"></a>final-Bezeichner
Können Sie die **endgültige** Schlüsselwort, um virtuelle Funktionen festzulegen, die in einer abgeleiteten Klasse überschrieben werden kann. Sie können es auch verwenden, um Klassen festzulegen, die nicht vererbbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
function-declaration final;  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Hinweise  
 **letzte** ist kontextbezogen und hat eine besonderen Bedeutung, nur, wenn er wird verwendet, nach der Deklaration einer Funktion oder Klasse; anderenfalls, es kein reserviertes Schlüsselwort ist.  
  
 Wenn **endgültige** wird verwendet, in den Klassendeklarationen `base-classes` ist ein optionaler Teil der Deklaration.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die **endgültige** Schlüsselwort, um anzugeben, dass eine virtuelle Funktion nicht überschrieben werden kann.  
  
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
  
 Weitere Informationen zur Verwendung, um anzugeben, dass Memberfunktionen überschrieben werden können, finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md).  
  
 Im nächsten Beispiel wird die **endgültige** Schlüsselwort, um anzugeben, dass eine Klasse nicht geerbt werden kann.  
  
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