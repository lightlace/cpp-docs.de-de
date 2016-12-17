---
title: "Befehlszeilenwarnung D9042"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "D9042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9042"
ms.assetid: d710693b-e422-40b2-b2dd-79e1b163b9e6
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "douge"
---
# Befehlszeilenwarnung D9042
Ungültiger Wert „value“ für „\/option“; „value“ wird angenommen; Codeanalysewarnungen sind in dieser Version des Compilers nicht verfügbar.  
  
 Die Nummer der Codeanalysewarnung wurde zur **\/wd**, **\/we**, **\/wo** oder **\/wl**\-Befehlszeilenoption hinzugefügt, und die **\/analyze**\-Befehlszeilenoption wurde auf einer Plattform angegeben, die keine Codeanalyse unterstützt. Um diese Warnung zu vermeiden, müssen Sie entweder die x86\-Version von Visual Studio Team System verwenden oder die **\/analyze**\-Befehlszeilenoption entfernen.  
  
## Beispiel  
 Im folgenden Befehlszeilenbeispiel wird die Warnung D9042 auf einem x64\- oder Itanium\-System generiert:  
  
```  
cl /EHsc /LD /wd6001 /analyze filename.cpp  
```  
  
 Um diese Warnung zu vermeiden, müssen Sie entweder die x86\-Version von Visual Studio Team System verwenden oder die **\/analyze**\- und **\/wd6001**\-Befehlszeilenoptionen entfernen.  
  
## Siehe auch  
 [Befehlszeilenfehler D8000 bis D9000](../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Compileroptionen](../build/reference/compiler-options.md)