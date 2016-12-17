---
title: "Deklaration von Eigenschaftenindizes"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Standardindexer"
  - "Standardwerte, Indexer"
  - "Indizierte Eigenschaften, C++"
  - "Indexer"
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Deklaration von Eigenschaftenindizes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax zum Deklarieren einer indizierten Eigenschaft hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Ein grundlegendes Defizit der Managed Extensions\-Programmiersprachenunterstützung für indizierte Eigenschaften ist die fehlende Unterstützung für eine Indizierung auf Klassenebene. Dies bedeutet, dass für alle indizierten Eigenschaften ein Name erforderlich ist und z. B. keine Möglichkeit besteht, einen verwalteten Indexoperator bereitzustellen, der direkt auf ein `Vector`\-Klassenobjekt oder ein `Matrix`\-Klassenobjekt angewendet werden kann.  Ein zweiter, weniger bedeutender Nachteil besteht darin, dass sich eine herkömmliche Eigenschaft visuell nur schwer von einer indizierten Eigenschaft unterscheiden lässt. Der einzige Anhaltspunkt ist die Anzahl der Parameter.  Schließlich haben indizierte Eigenschaften die gleichen Schwächen wie nicht indizierte Eigenschaften: Die Accessoren werden nicht als atomare Einheit behandelt, sondern in einzelne Methoden unterteilt.  Beispiel:  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 Beachten Sie, dass sich die Indexer nur durch die zusätzlichen Parameter unterscheiden, welche die Ein\- oder Zweidimensionalität eines Index angeben.  Nach der neuen Syntax lassen sich die Indexer anhand der Klammern \(\[,\]\) hinter dem Indexernamen unterscheiden, die die Nummer und den Typ eines jeden Index angeben:  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Um in der neuen Syntax einen Indexer auf Klassenebene anzugeben, der direkt auf Objekte der Klasse angewendet werden kann, wird das `default`\-Schlüsselwort erneut verwendet, um damit einen expliziten Namen zu ersetzen.  Beispiel:  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat …  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer …  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Wenn die indizierte Standardeigenschaft in der neuen Syntax angegeben wird, werden die beiden folgenden Namen reserviert: `get_Item` und `set_Item`.  Das liegt daran, dass es sich dabei um die zugrunde liegenden, für die indizierte Standardeigenschaft generierten Namen handelt.  
  
 Beachten Sie, dass es keine einfache Indexsyntax gibt, die zur einfachen Eigenschaftensyntax analog ist.  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Gewusst wie: Verwenden von indizierten Eigenschaften](../misc/how-to-use-indexed-properties.md)