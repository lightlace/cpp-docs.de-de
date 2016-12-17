---
title: "C++-Stack-Semantik f&#252;r Referenztypen"
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
  - "Verweistypen, C++-Stapelsemantik für"
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# C++-Stack-Semantik f&#252;r Referenztypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vor Visual C\+\+ 2005 konnte keine Instanz eines Referenztyps mithilfe des Operators `new` nur erstellt werden, der das Objekt auf dem Heap der Garbage Collection unterliegt erstellt hat.  Sie können eine Instanz eines Referenztyps mit der gleichen Syntax jetzt erstellen, die Sie verwenden, um eine Instanz eines systemeigenen Typs auf dem Stapel zu erstellen.  Daher ist es nicht erforderlich, um [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) zu verwenden, um ein Objekt aus einem Referenztyp zu erstellen.  Und wenn das Objekt den Gültigkeitsbereich verlässt, ruft der Compiler den Destruktor des Objekts auf.  
  
## Hinweise  
 Wenn Sie eine Instanz eines Referenztyps mithilfe der Stapelsemantik erstellen, erstellt der Compiler intern die Instanz auf dem Heap der Garbage Collection unterliegt \(mit `gcnew`\).  
  
 Wenn die Signatur oder der Rückgabetyp einer Funktion keine Instanz eines Referenztyps nach Wert enthält, wird die Funktion in den Metadaten als Benötigen der besondere Behandlung gekennzeichnet \(mit modreq\).  Diese besondere Behandlung wird dies nur von Visual C\+\+\-Clients bereitgestellt; andere Sprachen nicht unterstützen derzeit das Konsumieren von Funktionen oder Daten, die Referenztypen verwenden, die mit Stapelsemantik erstellt werden.  
  
 Ein Grund, `gcnew` \(dynamische Zuordnung\) anstelle der Stapelsemantik zu verwenden würde sein, wenn der Typ keinen Destruktor enthält.  Auch mit Referenztypen, die mit Stapelsemantik in den Funktionssignaturen erstellt wurden, sollten Sie nicht möglich, wenn Sie die Funktionen von anderen Sprachen als Visual C\+\+ verwendet werden soll.  
  
 Der Compiler erzeugt keinen Kopierkonstruktor für einen Referenztyp.  Wenn Sie eine Funktion definieren, die einen Verweistyp nach Wert in der Signatur verwendet, müssen Sie einen Kopierkonstruktor für den Referenztyp definieren.  Ein Kopierkonstruktor für einen Referenztyp weist eine Signatur der folgenden Form: `R(R%){}`.  
  
 Der Compiler erzeugt keinen standardmäßige Zuweisungsoperator für einen Referenztyp.  Ein Zuweisungsoperator ermöglicht es Ihnen, ein Objekt mit der Stapelsemantik zu erstellen und es mit einem vorhandenen Objekt initialisieren, das mithilfe der Stapelsemantik erstellt wird.  einen Zuweisungsoperator für einen Verweistyp weist eine Signatur der folgenden Form: `void operator=( R% ){}`.  
  
 Wenn der Destruktor des Typs wichtige Ressourcen und Sie Verwendungsstapelsemantik für Referenztypen ungebunden, müssen Sie nicht, den Destruktor explizit aufzurufen \(oder `delete`\) aufrufen.  Weitere Informationen zu Destruktoren in Verweistypen, finden Sie unter [Destruktoren und Finalizer in Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
 Ein vom Compiler generierter Zuweisungsoperator folgt den üblichen Standard\-C\+\+\-Regeln mit den folgenden Erweiterungen:  
  
-   Alle nicht statischen Datenmembern, deren Typ ein Handle zu einem Referenztyp, sind kopiert flaches \(behandelt wie ein nicht statischer Datenmember, dessen Typ einen Zeiger handelt\).  
  
-   Jeder nicht statische Datenmember, dessen Typ ein Werttyp ist, kopiert flaches.  
  
-   Jeder nicht statische Datenmember, dessen Typ eine Instanz eines Verweistyps ist, wird ein Aufruf an den Kopierkonstruktor des Referenztyps auf.  
  
 Der Compiler stellt außerdem einen `%` unären Operator, um eine Instanz eines Referenztyps zu konvertieren, der mit der Stapelsemantik zu seinem zugrunde liegenden Handletyp erstellt wird.  
  
 Die folgenden Verweistypen sind nicht zur Verwendung mit Stapelsemantik verfügbar:  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## Beispiel  
  
### **Beschreibung**  
 Das folgende Codebeispiel zeigt, wie Instanzen von Verweistypen mit Stapelsemantik, wie die Zuweisungsoperator\- und Kopierkonstruktorarbeiten deklariert und wie einen Nachverfolgungsverweis mit den Referenztyp initialisiert, der mithilfe der Stapelsemantik erstellt wird.  
  
### Code  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### Ausgabe  
  
```  
98  
98  
98  
13  
13  
```  
  
## Siehe auch  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)