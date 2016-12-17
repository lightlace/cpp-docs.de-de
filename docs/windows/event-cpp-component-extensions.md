---
title: "event  (C++ Component Extensions)"
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
  - "event"
  - "event_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event keyword [C++]"
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
caps.latest.revision: 34
caps.handback.revision: "32"
ms.author: "mblome"
manager: "ghogen"
---
# event  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `event`\-Schlüsselwort deklariert ein *Ereignis*, d. h. eine Benachrichtigung an die registrierten Abonnenten \(*Ereignishandler*\), dass etwas geschehen ist, das für sie von Interesse ist.  
  
## Alle Laufzeiten  
 C\+\+\/CX unterstützt das Deklarieren eines *Ereignismember* oder eines *Event\-Blocks*.  Ein Ereignismember ist die Kurzschreibweise für das Deklarieren eines Event\-Blocks.  Standardmäßig deklariert ein Ereignismember die Funktionen `add()`, `remove()` und `raise()`, die explizit in einem Event\-Block deklariert werden.  Um die Funktionen in einem Ereignismember anzupassen, deklarieren Sie stattdessen einen Event\-Block und überschreiben Sie dann die Funktionen, die Sie benötigen.  
  
 **Syntax**  
  
```  
  
// event data member  
modifier event delegate^ event_name;     
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **Parameter**  
  
 *modifier*  
 Ein Modifizierer, der entweder für die Ereignisdeklaration oder eine Ereignisaccessormethode verwendet werden kann.  Mögliche Werte sind `static` und `virtual`.  
  
 *delegate*  
 Der [Delegat](../windows/delegate-cpp-component-extensions.md), mit dessen Signatur der Ereignishandler übereinstimmen muss.  
  
 *event\_name*  
 Der Name des Ereignisses.  
  
 *return\_value*  
 Der Rückgabewert der Ereignisaccessormethode.  Um überprüfbar zu sein, muss der Rückgabetyp `void` sein.  
  
 *parameters*  
 \(optional\) Parameter für die `raise`\-Methode, die mit der Signatur des Parameters *delegate* übereinstimmen.  
  
 **Hinweise**  
  
 Ein Ereignis ist eine Zuordnung zwischen einem Delegaten und einer Memberfunktion \(Ereignishandler\), die auf das Auslösen des Ereignisses reagiert und es Clients beliebiger Klassen ermöglicht, Methoden zu registrieren, die mit der Signatur und dem Rückgabetyp des zugrundeliegenden Delegaten übereinstimmen.  
  
 Es gibt zwei Arten von Ereignisdeklarationen:  
  
 *event data member*  
 Der Compiler erstellt automatisch Speicherplatz für das Ereignis in Form eines Members des Delegattyps und erstellt interne Memberfunktionen `add()`, `remove()` und `raise()`.  Ein Ereignisdatenmember muss innerhalb einer Klasse deklariert werden.  Der Rückgabetyp des Rückgabetyps des Delegaten muss dem Rückgabetyp des Ereignishandlers entsprechen.  
  
 *event block*  
 Ein Event\-Block ermöglicht es Ihnen, das Verhalten der Methoden `add()`, `remove()` und `raise()` explizit zu deklarieren und anzupassen.  
  
 Sie können mithilfe von `operators+=` und `operator-=` einen Ereignishandler hinzufügen und entfernen oder die Methoden `add()` und `remove()` explizit aufrufen.  
  
 `event` ist ein kontextbezogenes Schlüsselwort. Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Hinweise  
 Weitere Informationen finden Sie unter [Ereignisse \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx).  
  
 Wenn Sie beabsichtigen, einen Ereignishandler hinzuzufügen und dann zu entfernen, müssen Sie die EventRegistrationToken\-Struktur speichern, die durch den Vorgang des Hinzufügens zurückgegeben wird.  Dann müssen Sie im Entfernungsvorgang die gespeicherte EventRegistrationToken\-Struktur verwenden, um den zu entfernenden Ereignishandler zu identifizieren.  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Mit dem `event`\-Schlüsselwort können Sie ein Ereignis deklarieren.  Ein Ereignis ist eine Methode, anhand derer eine Klasse Benachrichtigungen übermitteln kann, wenn etwas von Interesse geschieht.  
  
 **Syntax**  
  
```  
  
// event data member  
modifier event delegate^ event_name;   
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **Parameter**  
  
 *modifier*  
 Ein Modifizierer, der entweder für die Ereignisdeklaration oder eine Ereignisaccessormethode verwendet werden kann.  Mögliche Werte sind `static` und `virtual`.  
  
 *delegate*  
 Der [Delegat](../windows/delegate-cpp-component-extensions.md), mit dessen Signatur der Ereignishandler übereinstimmen muss.  
  
 *event\_name*  
 Der Name des Ereignisses.  
  
 *return\_value*  
 Der Rückgabewert der Ereignisaccessormethode.  Um überprüfbar zu sein, muss der Rückgabetyp `void` sein.  
  
 *parameters*  
 \(optional\) Parameter für die `raise`\-Methode, die mit der Signatur des Parameters *delegate* übereinstimmen.  
  
 **Hinweise**  
  
 Ein Ereignis ist eine Zuordnung zwischen einem Delegaten und einer Memberfunktion \(Ereignishandler\), die auf das Auslösen des Ereignisses reagiert und es Clients beliebiger Klassen ermöglicht, Methoden zu registrieren, die mit der Signatur und dem Rückgabetyp des zugrundeliegenden Delegaten übereinstimmen.  
  
 Der Delegat kann eine oder mehrere zugeordnete Methoden haben, die aufgerufen werden, wenn der Code angibt, dass das Ereignis aufgetreten ist.  Ein Ereignis in einem Programm kann für andere Programme verfügbar gemacht werden, die auf die .NET Framework Common Language Runtime abzielen.  Ein Beispiel finden Sie unter [Auslösen eines in einer anderen Assembly definierten Ereignisses](../misc/how-to-raise-events-defined-in-a-different-assembly.md).  
  
 Es gibt zwei Arten von Ereignisdeklarationen:  
  
 *event data members*  
 Speicher für das Ereignis in der Form eines Members des Delegattyps wird vom Compiler für Datenmemberereignisse erstellt.  Ein Ereignisdatenmember muss innerhalb einer Klasse deklariert werden.  Dies wird auch als triviales Ereignis bezeichnet \(siehe untenstehendes Codebeispiel\).  
  
 *event blocks*  
 Über Ereignis\-Blöcke können Sie das Verhalten der Add\-, Remove\- und Raise\-Methoden anpassen, indem Sie Add\-, Remove\- und Raise\-Methoden implementieren.  Die Signatur der Add\-, Remove\- und Raise\-Methoden muss mit der Signatur des Delegaten übereinstimmen.  Event\-Block\-Ereignisse sind keine Datenmember und jede Verwendung als Datenmember führt zu einem Compilerfehler.  Ein Beispiel finden Sie unter [Definieren von Ereignisaccessormethoden](../misc/how-to-define-event-accessor-methods.md).  
  
 Der Rückgabetyp des Ereignishandlers muss dem Rückgabetyp des Delegaten entsprechen.  
  
 In .NET Framework können Sie einen Datenmember behandeln, als wäre er eine Methode selbst \(d. h. die `Invoke`\-Methode des entsprechenden Delegaten\).  Sie müssen den Delegattyp vordefinieren, um einen verwalteten Ereignisdatenmember zu deklarieren.  Im Gegensatz dazu definiert eine verwaltete Ereignismethode implizit den entsprechenden verwalteten Delegaten, sofern er noch nicht definiert ist.  Ein Codebeispiel finden Sie am Ende dieses Themas.  
  
 Wenn Sie ein verwaltetes Ereignis deklarieren, können Sie add\- und remove\-Accessoren angeben, die aufgerufen werden, wenn Ereignishandler über die Operatoren \+\= und \-\= hinzugefügt oder entfernt werden.  Die Add\-, Remove\- und Raise\-Methoden können explizit aufgerufen werden.  
  
 Die folgenden Schritte müssen durchgeführt werden, um Ereignisse in Visual C\+\+ zu erstellen und zu verwenden:  
  
1.  Erstellen oder Identifizieren eines Delegaten.  Wenn Sie ein eigenes Ereignis definieren, müssen Sie auch sicherstellen, dass es einen Delegaten für die Verwendung mit dem `event`\-Schlüsselwort gibt.  Wenn das Ereignis vordefiniert ist, beispielsweise in .NET Framework, müssen die Consumer des Ereignisses lediglich den Namen des Delegaten kennen.  
  
2.  Erstellen Sie eine Klasse, die Folgendes enthält:  
  
    -   Ein aus dem Delegaten erstelltes Ereignis.  
  
    -   \(optional\) Eine Methode, die überprüft, dass eine Instanz des mit dem `event`\-Schlüsselwort deklarierten Delegaten vorhanden ist.  Andernfalls muss diese Logik im Code eingefügt werden, durch den das Ereignis ausgelöst wird.  
  
    -   Methoden, die das Ereignis aufrufen.  Diese Methoden können Überschreibungen von Funktionen der Basisklasse sein.  
  
     Diese Klasse definiert das Ereignis.  
  
3.  Definieren Sie eine oder mehrere Klassen, die Methoden mit dem Ereignis verbinden.  Jede dieser Klassen ordnet dem Ereignis in der Basisklasse eine oder mehrere Methoden zu.  
  
4.  Verwenden Sie das Ereignis:  
  
    -   Erstellen Sie ein Objekt der Klasse, die die Ereignisdeklaration enthält.  
  
    -   Erstellen Sie ein Objekt der Klasse, die die Ereignisdefinition enthält.  
  
 Weitere Informationen zu [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]\-Ereignissen finden Sie unter  
  
-   [Ereignisse in einer Schnittstelle](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
-   [Überschreiben des Standardzugriffs von Add\-, Remove\- und Raise\-Methoden](../misc/how-to-override-default-access-of-add-remove-and-raise-methods.md)  
  
-   [Mehrere Handler für ein Ereignis](../misc/how-to-add-multiple-handlers-to-events.md)  
  
-   [Verwaltete virtuelle Ereignisse](../misc/how-to-implement-managed-virtual-events.md)  
  
-   [Ereignisaccessormethoden](../misc/how-to-define-event-accessor-methods.md)  
  
-   [Statische Ereignisse](../misc/how-to-define-and-use-static-events.md)  
  
-   [Auslösen eines in einer anderen Assembly definierten Ereignisses](../misc/how-to-raise-events-defined-in-a-different-assembly.md)  
  
-   [Abstrakte Ereignisse](../misc/how-to-implement-abstract-events.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird das Deklarieren von Paaren von Delegaten, Ereignissen und Ereignishandlers veranschaulicht, das Abonnieren \(Hinzufügen\) der Ereignishandler, das Aufrufen der Ereignishandler und dann das Kündigen des Abonnements \(Entfernen\) der Ereignishandler.  
  
```  
// mcppv2_events.cpp  
// compile with: /clr  
using namespace System;  
  
// declare delegates  
delegate void ClickEventHandler(int, double);  
delegate void DblClickEventHandler(String^);  
  
// class that defines events  
ref class EventSource {  
public:  
   event ClickEventHandler^ OnClick;   // declare the event OnClick  
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick  
  
   void FireEvents() {  
      // raises events  
      OnClick(7, 3.14159);  
      OnDblClick("Hello");  
   }  
};  
  
// class that defines methods that will called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
  
   void OnMyDblClick(String^ str) {  
      Console::WriteLine("OnDblClick: {0}", str);  
   }  
};  
  
int main() {  
   EventSource ^ MyEventSource = gcnew EventSource();  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
  
   // invoke events  
   MyEventSource->FireEvents();  
  
   // unhook handler to event  
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
}  
```  
  
 **Ausgabe**  
  
  **OnClick: 7, 3.14159**  
 **OnDblClick: Hello** **Beispiel**  
  
 Im folgenden Codebeispiel wird die Logik zum Generieren der `raise`\-Methode eines trivialen Ereignisses veranschaulicht: Wenn das Ereignis einen oder mehrere Abonnenten aufweist, wird beim impliziten oder expliziten Aufrufen der `raise`\-Methode der Delegat aufgerufen.  Wenn der Rückgabetyp des Delegattyps nicht `void` lautet und es keine Ereignisabonnenten gibt, gibt die `raise`\-Methode den Standardwert für den Delegattyp zurück.  Wenn keine Ereignisabonnenten vorhanden sind, wird beim Aufrufen der `raise`\-Methode einfach zurückgegeben und keine Ausnahme ausgelöst.  Wenn der Rückgabetyp des Delegaten nicht `void` lautet, wird der Delegattyp zurückgegeben.  
  
```  
// trivial_events.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int Del();  
public ref struct C {  
   int i;  
   event Del^ MyEvent;  
  
   void FireEvent() {  
      i = MyEvent();  
   }  
};  
  
ref struct EventReceiver {  
   int OnMyClick() { return 0; }  
};  
  
int main() {  
   C c;  
   c.i = 687;  
  
   c.FireEvent();  
   Console::WriteLine(c.i);  
   c.i = 688;  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);  
   Console::WriteLine(c.i);     
}  
```  
  
 **Ausgabe**  
  
  **0**  
 **688**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)