---
title: "nothrow (C++)"
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
  - "nothrow_cpp"
  - "nothrow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], nothrow"
  - "nothrow __declspec-Schlüsselwort"
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# nothrow (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ein erweitertes `__declspec`\-Attribut, das in der Deklaration von Funktionen verwendet werden kann.  
  
## Syntax  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## Hinweise  
 Dieses Attribut weist den Compiler an, dass die deklarierte Funktion und die Funktionen, die aufgerufen werden, nie eine Ausnahme auslösen.  Mit dem Modell für synchrone Ausnahmebehandlung kann der Compiler nun standardmäßig die Mechanismen der Lebensdauerverfolgung gewisser entladbarer Objekte in einer solchen Funktion eliminieren, wodurch die Codegröße erheblich reduziert wird.  Bei der Präprozessordirektive sind die folgenden drei Funktionsdeklarationen gleichwertig:  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 Die Verwendung von `void __declspec(nothrow) __stdcall f2();` hat den Vorteil, dass Sie eine API\-Definition verwenden können, wie die von der `#define`\-Anweisung veranschaulichte Definition, um `nothrow` auf einem Satz von Funktionen anzugeben.  Die dritte Deklaration`, void __stdcall f3() throw();` ist die Syntax, die vom C\+\+\-Standard definiert wird.  
  
 Weitere Informationen erhalten Sie unter [Synchrone Ausnahmebehandlung](assetId:///81595fae-d8ab-4c14-9670-8d6639cc0369).  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)