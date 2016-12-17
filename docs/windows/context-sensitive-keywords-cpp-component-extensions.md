---
title: "Kontextbezogene Schl&#252;sselw&#246;rter (Komponentenerweiterungen f&#252;r C++)"
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
  - "internal_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kontextbezogene Schlüsselwörter"
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "mblome"
manager: "ghogen"
---
# Kontextbezogene Schl&#252;sselw&#246;rter (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*Kontextbezogene Schlüsselwörter* sind Sprachelemente, die nur in bestimmten Kontexten erkannt werden.  Außerhalb des jeweiligen Kontexts kann ein kontextbezogenes Schlüsselwort ein benutzerdefiniertes Symbol sein.  
  
## Alle Laufzeiten  
 **Hinweise**  
  
 Die folgende Liste enthält die kontextbezogenen Schlüsselwörter:  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [Ereignis](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal` \(siehe [Membersichtbarkeit](../misc/member-visibility.md)\)  
  
-   [literal](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [Eigenschaft](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` \(Teil von [Generics](../windows/generics-cpp-component-extensions.md)\)  
  
 Um die Lesbarkeit zu erhöhen, sollten Sie die Verwendung von kontextbezogenen Schlüsselwörtern als benutzerdefinierte Symbole einschränken.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 \(Es gibt keine plattformspezifischen Hinweise für diese Funktion.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 \(Es gibt keine plattformspezifischen Hinweise für diese Funktion.\)  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird dargestellt, wie das kontextbezogene Schlüsselwort `property` im entsprechenden Kontext verwendet werden kann, um eine Eigenschaft und eine Variable zu definieren.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Ausgabe**  
  
  **100**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)