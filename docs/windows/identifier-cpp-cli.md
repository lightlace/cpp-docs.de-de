---
title: "__identifier (C++/CLI)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__identifier"
  - "__identifier_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__identifier keyword [C++]"
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# __identifier (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die Verwendung von Visual C\+\+\-Schlüsselworten als Bezeichner.  
  
## Alle Plattformen  
 **Syntax**  
  
```  
  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
 **Hinweise**  
  
 Verwendung des `__identifier`\-Schlüsselwort für Bezeichner, die keine Schlüsselwörter sind, ist zulässig, jedoch abgeraten stark wie eine Frage des Stils.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird eine Klasse, die `template`, in C\# erstellt und verteilt als DLL.  Im Visual C\+\+\-Programm, das die `template`\-Klasse verwendet, wird das `__identifier`\-Schlüsselwort der Tatsache, dass `template` ein Standard\-C\+\+\-Schlüsselwort ist.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 Das Schlüsselwort `__identifier` ist mit den Compileroptionen **\/clr** und **\/clr:oldSyntax** zulässig.  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird eine Klasse, die `template`, in C\# erstellt und verteilt als DLL.  Im Visual C\+\+\-Programm, das die `template`\-Klasse verwendet, wird das `__identifier`\-Schlüsselwort der Tatsache, dass `template` ein Standard\-C\+\+\-Schlüsselwort ist.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)