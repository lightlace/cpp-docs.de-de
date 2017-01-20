---
title: "Platform, default, and cli Namespaces  (C++ Component Extensions)"
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
  - "lang"
  - "cli"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lang namespace"
  - "cli namespace"
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# Platform, default, and cli Namespaces  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Namespace qualifiziert die Namen von Sprachelementen, sodass sie keinen Konflikt mit ansonsten identischen Namen an anderer Stelle im Quellcode verursachen.  Beispielsweise kann ein Namenskonflikt verhindern, dass der Compiler [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md) erkennt.  Namespaces werden vom Compiler verwendet, jedoch nicht in der kompilierten Assembly beibehalten.  
  
## Alle Laufzeiten  
 Beim Erstellen des Projekts stellt Visual C\+\+ einen Standardnamespace für das Projekt bereit.  Sie können den Namespace manuell umbenennen, obwohl der Name der WINMD\-Datei in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] mit dem Namen des Stammnamespace übereinstimmen muss.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Weitere Informationen finden Sie unter [Namespaces und Typsichtbarkeit \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx)..  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntax**  
  
```  
using namespace cli;  
```  
  
 **Hinweise**  
  
 Der [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] unterstützt den `cli`\-Namespace.  Beim Kompilieren mit **\/clr** ist die `using`\-Anweisung im Syntaxabschnitt enthalten.  
  
 Die folgenden Sprachfunktionen sind im `cli`\-Namespace:  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, dass es möglich ist, ein Symbol im `cli`\-Namespace als benutzerdefiniertes Symbol im Code zu verwenden.  Sobald dies geschehen ist, müssen Sie die Verweise jedoch explizit oder implizit auf das `cli`\-Sprachelement des gleichen Namens qualifizieren.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)