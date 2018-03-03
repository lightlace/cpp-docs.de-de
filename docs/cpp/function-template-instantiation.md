---
title: Funktion Vorlageninstanziierung | Microsoft Docs
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
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41bf7f6ba3a2a17c6355ee9239cadb6e5014ee96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="function-template-instantiation"></a>Funktionsvorlageninstanziierung
Wenn eine Funktionsvorlage für einen Typ das erste Mal aufgerufen wird, erstellt der Compiler eine Instanziierung. Jede Instanziierung ist eine Version der auf Vorlagen basierenden Funktion, die auf den Typ spezialisiert wurde. Diese Instanziierung wird jedes Mal aufgerufen, wenn die Funktion für den Typ verwendet wird. Wenn Sie über mehrere identische Instanziierungen verfügen (auch in verschiedenen Modulen), ist nur eine Kopie der Instanziierung in der ausführbaren Datei enthalten.  
  
 Konvertierung von Funktionsargumenten ist in den Funktionsvorlagen für alle Argument- und Parameterpaare zulässig, in denen der Parameter nicht von einem Vorlagenargument abhängt.  
  
 Funktionsvorlagen können explizit instanziiert werden, indem die Vorlage mit einem bestimmten Typ als Argument deklariert wird. Es ist beispielsweise der folgende Code zulässig:  
  
```cpp
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)
