---
title: "Delegaten und Ereignisse"
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
  - "__delegate-Schlüsselwort"
  - "__event-Schlüsselwort [C++]"
  - "delegate-Schlüsselwort [C++]"
  - "Delegaten [C++], Aktualisieren von Managed Extensions for C++"
  - "event-Schlüsselwort [C++]"
  - "Ereignisse [C++], Aktualisieren von Managed Extensions for C++"
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Delegaten und Ereignisse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Art und Weise, Delegaten und Ereignisse zu deklarieren, hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Der doppelte Unterstrich ist nicht mehr erforderlich, wie aus dem folgenden Beispiel ersichtlich wird.  Hier ein Beispielcode in Managed Extensions:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 Der gleiche Code sieht in der neuen Syntax folgendermaßen aus:  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 Ereignisse \(und Delegaten\) sind Referenztypen. Dies ist in der neuen Syntax an dem Hut \(`^`\) klar zu erkennen.  Ereignisse unterstützen im voranstehenden Code sowohl eine explizite Deklarationssyntax als auch die normale Form.  Bei der expliziten Form gibt der Benutzer die dem Ereignis zugeordnete `add`\-Methode, `raise`\-Methode und `remove`\-Methode an. \(Nur die `add`\-Methode und die `remove`\-Methode sind erforderlich; die `raise`\-Methode ist optional.\)  
  
 Wenn Sie diese Methoden in Managed Extensions zur Verfügung stellen möchten, müssen Sie zwar keine explizite Ereignisdeklaration bereitstellen, aber trotzdem einen Namen für das nicht vorhandene Ereignis wählen.  Jede Methode wird in der Form `add_EventName`, `raise_EventName` und `remove_EventName` angegeben, wie im folgenden Beispiel aus der Spezifikation für Managed Extensions gezeigt wird:  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 Die neue Syntax vereinfacht hingegen die Deklaration, wie die folgende Übersetzung veranschaulicht.  Ein Ereignis gibt die zwei oder drei Methoden in Klammern an, die unmittelbar hinter der Deklaration des Ereignisses und dessen zugeordnetem Delegattyp wie folgt eingefügt werden:  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [delegate](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)