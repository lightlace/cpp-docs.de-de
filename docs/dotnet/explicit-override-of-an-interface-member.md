---
title: "Explizites &#220;berschreiben eines Schnittstellenmembers | Microsoft Docs"
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
  - "Explizites Überschreiben von virtuellen Funktionen"
  - "Funktionen [C++], Überschreiben"
  - "Schnittstellenmember, Explizite Überschreibungen"
  - "Überschreiben von Funktionen"
  - "Virtuelle Funktionen, Explizite Überschreibungen"
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Explizites &#220;berschreiben eines Schnittstellenmembers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax für das Deklarieren einer expliziten Überschreibung eines Schnittstellenmembers innerhalb einer Klasse hat sich gegenüber Managed Extensions for C\+\+ in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] geändert.  
  
 Oft ist es von Vorteil, zwei Instanzen eines Schnittstellenmembers innerhalb einer Klasse bereitzustellen, die die Schnittstelle implementiert – eine Instanz wird verwendet, wenn Klassenobjekte über einen Schnittstellenhandler bearbeitet werden, die andere, wenn Klassenobjekte über die Klassenschnittstelle verwendet werden.  Beispiel:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 In Managed Extensions geschieht dies durch Bereitstellen einer expliziten Deklaration der Schnittstellenmethode mit dem Methodennamen, der mit dem Namen der Schnittstelle qualifiziert wird.  Die klassenspezifische Instanz ist nicht qualifiziert.  Auf diese Weise muss in dem Beispiel der Rückgabewert von `Clone` nicht mehr umgewandelt werden, wenn er explizit über eine Instanz von `R` aufgerufen wird.  
  
 In der neuen Syntax wurde ein allgemeiner Überschreibungsmechanismus eingeführt, der die Managed Extensions\-Syntax ersetzt.  Das Beispiel würde wie folgt umgeschrieben werden:  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Diese Korrektur erfordert, dass der explizit überschriebene Schnittstellenmember einen eindeutigen Namen in der Klasse erhält.  Hier wurde der komplizierte Name `InterfaceClone` bereitgestellt.  Das Verhalten bleibt gleich – über die `ICloneable`\-Schnittstelle wird der umbenannte `InterfaceClone,` aufgerufen, während über ein Objekt vom Typ `R` die zweite `Clone`\-Instanz aufgerufen wird.  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)