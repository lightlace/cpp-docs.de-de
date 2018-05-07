---
title: Delegaten und Ereignisse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- delegate keyword [C++]
- delegates [C++], upgrading from Managed Extensions for C++
- __delegate keyword
- events [C++], upgrading from Managed Extensions for C++
- event keyword [C++]
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 69e0ffcb9b9c48de152a383b4b9a3f6edbe99f42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="delegates-and-events"></a>Delegaten und Ereignisse
Die Möglichkeit zum Deklarieren von Delegaten und Ereignisse wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 Der doppelte Unterstrich wird nicht mehr benötigt, wie im folgenden Beispiel gezeigt. Hier ein Beispielcode in Managed Extensions:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 Der gleiche Code in der neuen Syntax sieht wie folgt aus:  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 Ereignisse (und Delegaten) sind Referenztypen, die aufgrund der Verwendung von der Hat löschen in der neuen Syntax ist (`^`).  Ereignisse unterstützen eine explizite Deklarationssyntax und die normale Form im vorangehenden Code dargestellt. In die explizite Form der Benutzer gibt die `add`, `raise`, und `remove` Methoden, die dem Ereignis zugeordnet. (Nur die `add` und `remove` Methoden sind erforderlich; die `raise` Methode ist optional.)  
  
 In Managed Extensions, wenn Sie diese Methoden bereitstellen, müssen Sie auch keinen explizite Ereignisdeklaration, aber Sie müssen entscheiden, einen Namen für das Ereignis, das nicht vorhanden ist. Jede Methode wird angegeben, in der Form `add_EventName`, `raise_EventName`, und `remove_EventName`, wie im folgenden Beispiel stammt aus der Spezifikation von Managed Extensions:  
  
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
  
 Die neue Syntax vereinfacht die Deklaration, wie die folgende Übersetzung veranschaulicht. Ein Ereignis gibt an, die zwei oder drei Methoden in einem Paar geschweifter Klammern eingeschlossen und sofort nach der Deklaration des Ereignisses und seiner zugeordneten Delegattyp platziert werden, wie hier gezeigt:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Delegate (Komponentenerweiterungen für C++)](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)