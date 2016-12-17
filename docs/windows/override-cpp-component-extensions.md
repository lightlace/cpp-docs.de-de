---
title: "override  (C++ Component Extensions)"
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
  - "overriding, override keyword [C++]"
  - "override keyword [C++]"
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# override  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das kontextbezogene `override`\-Schlüsselwort gibt an, dass ein Member eines Typs eine Basisklasse oder einen Basisschnittstellenmember überschreibt.  
  
## Hinweise  
 Das `override`\-Schlüsselwort ist beim Kompilieren für systemeigene Ziele \(standardmäßige Compileroption\), für Windows\-Runtime\-Ziele \(**\/ZW**\-Compileroption\) oder Common Language Runtime\-Ziele \(**\/clr**\-Compileroption\) gültig.  
  
 Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter [override\-Bezeichner](../cpp/override-specifier.md) und [Überschreibungsspezifizierer und systemeigene Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## Beispiele  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in systemeigenen Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in Windows\-Runtime\-Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Voraussetzungen**  
  
 Compileroption: **\/ZW**  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in Common Language Runtime\-Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Voraussetzungen**  
  
 Compileroption: **\/clr**  
  
## Siehe auch  
 [override\-Bezeichner](../cpp/override-specifier.md)   
 [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)