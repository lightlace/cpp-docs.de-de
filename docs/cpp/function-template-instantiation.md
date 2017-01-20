---
title: "Funktionsvorlageninstanziierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionsvorlagen, Instanziierung"
  - "Instanziierung, Funktionsvorlagen"
  - "Vorlagen, Instanziierung"
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsvorlageninstanziierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Funktionsvorlage für einen Typ das erste Mal aufgerufen wird, erstellt der Compiler eine Instanziierung.  Jede Instanziierung ist eine Version der auf Vorlagen basierenden Funktion, die auf den Typ spezialisiert wurde.  Diese Instanziierung wird jedes Mal aufgerufen, wenn die Funktion für den Typ verwendet wird.  Wenn Sie über mehrere identische Instanziierungen verfügen \(auch in verschiedenen Modulen\), ist nur eine Kopie der Instanziierung in der ausführbaren Datei enthalten.  
  
 Konvertierung von Funktionsargumenten ist in den Funktionsvorlagen für alle Argument\- und Parameterpaare zulässig, in denen der Parameter nicht von einem Vorlagenargument abhängt.  
  
 Funktionsvorlagen können explizit instanziiert werden, indem die Vorlage mit einem bestimmten Typ als Argument deklariert wird.  Es ist beispielsweise der folgende Code zulässig:  
  
```  
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
  
## Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)