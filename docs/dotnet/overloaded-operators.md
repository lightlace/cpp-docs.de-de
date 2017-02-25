---
title: "&#220;berladene Operatoren | Microsoft Docs"
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
  - "Operatoren überladen, In einer CLR-Klasse"
  - "Operatoren [C++], Überladen"
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# &#220;berladene Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Überladen von Operatoren hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] im Vergleich zu Managed Extensions for C\+\+ wesentlich geändert.  
  
 Bei der Deklaration eines Referenztyps kann beispielsweise nicht die systemeigene `operator+`\-Syntax verwendet werden, sondern es muss der zugrunde liegende interne Name des Operators explizit ausgeschrieben werden – in diesem Fall ist dies `op_Addition`.  Darüber hinaus muss der Aufruf eines Operators explizit über diesen Namen erfolgen, wodurch die zwei Hauptvorteile des Überladens von Operatoren bedeutungslos werden: \(a\) die intuitive Syntax und \(b\) die Möglichkeit, neue und vorhandene Typen zu kombinieren.  Beispiel:  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 In der neuen Syntax erfolgen die Deklaration und die Verwendung von statischen Operatoren wieder so, wie es C\+\+\-Programmierer ursprünglich gewohnt waren.  Das folgende Beispiel zeigt die `Vector`\-Klasse übersetzt in die neue Syntax:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)