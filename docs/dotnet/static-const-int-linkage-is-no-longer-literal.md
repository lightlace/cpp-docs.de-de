---
title: "Die Bindung von static&#160;const&#160;int-Membern ist nicht mehr literal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstanten, Deklarieren"
  - "Integralkonstanten-Ausdrücke"
  - "Literalattribut [C++]"
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Die Bindung von static&#160;const&#160;int-Membern ist nicht mehr literal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Deklaration eines konstanten Members einer Klasse hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Zwar werden ganzzahlige `static const`\-Member weiterhin unterstützt, jedoch hat sich ihr Bindungsattribut geändert.  Ihr früheres Bindungsattribut ist jetzt Teil eines literalen, ganzzahligen Members.  Betrachten Sie z. B. die folgende Managed Extensions\-Klasse:  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Damit werden die folgenden zugrunde liegenden CIL\-Attribute für das Feld generiert \(beachten Sie das literale Attribut\):  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Dagegen wird folgende Klasse unter der neuen Syntax immer noch kompiliert:  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Das literale Attribut wird nicht mehr ausgegeben und deshalb von der CLR\-Laufzeit auch nicht als Konstante behandelt:  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Um das gleiche, sprachenübergreifende literale Attribut zu erhalten, müssen Sie die Deklaration in den neu unterstützten `literal`\-Datenmember ändern:  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [literal](../windows/literal-cpp-component-extensions.md)