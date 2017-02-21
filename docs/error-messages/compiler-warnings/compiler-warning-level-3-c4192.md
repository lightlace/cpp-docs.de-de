---
title: "Compilerwarnung (Stufe 3) C4192 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4192"
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 3) C4192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Automatischer Ausschluss von 'Name' während des Importierens der Typbibliothek 'Bibliothek'  
  
 Eine `#import`\-Bibliothek enthält ein Element *Name*, das auch in den Win32\-Systemheadern definiert ist.  Aufgrund von Beschränkungen für Typbibliotheken werden Namen wie **IUnknown** oder GUID oft in einer Typbibliothek definiert, indem die Definition aus den Systemheadern dupliziert wird.  `#import` erkennt diese Elemente und verhindert deren Einbindung in die TLH\- und TLI\-Headerdateien.  
  
 Wenn Sie dieses Verhalten umgehen möchten, verwenden Sie die `#import`\-Attribute [no\_auto\_exclude](../../preprocessor/no-auto-exclude.md) und [include\(\)](../../preprocessor/include-parens.md).