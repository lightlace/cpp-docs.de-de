---
title: "Deklaration eines CLR-Arrays | Microsoft Docs"
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
  - "array-Schlüsselwort [C++]"
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Deklaration eines CLR-Arrays
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax zum Deklarieren, Instanziieren und Initialisieren eines verwalteten Arrays hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] im Vergleich zu Managed Extensions for C\+\+ geändert.  
  
 Die Deklaration eines CLR\-Arrayobjekts in Managed Extensions bestand in einer Erweiterung der standardmäßigen Arraydeklaration, bei der ein `__gc`\-Schlüsselwort zwischen dem Namen des Arrayobjekts und dessen möglicherweise kommagefüllter Dimension eingefügt wurde, wie in den folgenden zwei Beispielen gezeigt wird:  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 Dies wurde in der neuen Syntax vereinfacht, in der nun eine vorlagenartige Deklaration verwendet wird, ähnlich der STL\-`vector`\-Deklaration.  Der erste Parameter gibt den Elementtyp an.  Der zweite Parameter gibt die Dimension des Arrays an \(mit einem Standardwert von 1, sodass nur bei mehrdimensionalen Arrays ein zweites Argument erforderlich ist\).  Das Arrayobjekt selbst ist ein Trackinghandle und muss deshalb mit einem Hut versehen werden.  Wenn der Elementtyp auch ein Referenztyp ist, muss dieser ebenfalls mit einem Hut versehen werden.  Das obige Beispiel sieht in der neuen Syntax beispielsweise wie folgt aus:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 Da ein Referenztyp eher ein Trackinghandle als ein Objekt ist, ist es möglich, ein CLR\-Array als den Rückgabetyp einer Funktion anzugeben. \(Es ist hingegen nicht möglich, das systemeigene Array als den Rückgabetyp einer Funktion anzugeben.\) Die Syntax war in dieser Hinsicht in Managed Extensions etwas unintuitiv.  Beispiel:  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 In [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] ist die Deklaration deutlich einfacher.  Beispiel:  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 Die Kurznotation für die Initialisierung eines lokalen verwalteten Arrays wird in beiden Versionen der Sprache unterstützt.  Beispiel:  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 wurde in der neuen Syntax wesentlich vereinfacht \(beachten Sie, dass aufgrund des impliziten Boxings in der neuen Syntax der Operator `__box` entfernt wurde – Erläuterungen hierzu finden Sie unter [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)\):  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 Da ein Array ein CLR\-Referenztyp ist, ist die Deklaration jedes Arrayobjekts ein Trackinghandle.  Deshalb müssen Arrayobjekte auf dem CLR\-Heap reserviert werden. \(Die Kurznotation blendet die verwaltete Heapreservierung aus.\) Nachfolgend steht die explizite Form der Initialisierung eines Arrayobjekts in Managed Extensions:  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 In der neuen Syntax wurde der `new`\-Ausdruck durch `gcnew` ersetzt.  Die Dimensionsgrößen werden wie folgt als Parameter an den `gcnew`\-Ausdruck übergeben:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 In der neuen Syntax kann dem `gcnew`\-Ausdruck eine explizite Initialisierungsliste folgen; diese Möglichkeit wurde in Managed Extensions nicht unterstützt.  Beispiel:  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## Siehe auch  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)