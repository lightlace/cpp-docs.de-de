---
title: "Gewusst wie: Definieren und Installieren eines globalen Ausnahmehandlers | Microsoft Docs"
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
  - "Handler, Global"
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gewusst wie: Definieren und Installieren eines globalen Ausnahmehandlers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird veranschaulicht, wie Ausnahmen erfasst werden können.  Das Beispielsformular enthält eine Schaltfläche, die, falls sie gedrückt wird, einen NULL\-Verweis ausführt und bewirkt eine Ausnahme ausgelöst.  Diese Funktion stellt einen typischen Codefehler dar.  Die resultierende Ausnahme wird vom Ausnahmehandler anwendungsweiten abgefangen, der von der Hauptfunktion installiert ist.  
  
 Dies wird erreicht, indem einen Delegaten dem <xref:System.Windows.Forms.Application.ThreadException>\-Ereignis bindet.  In diesem Fall wird folgende Ausnahmen dann zur `App::OnUnhandled`\-Methode gesendet.  
  
## Beispiel  
  
```  
// global_exception_handler.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Drawing;  
using namespace System::Windows::Forms;  
  
ref class MyForm : public Form  
{  
   Button^ b;  
public:  
   MyForm( )  
   {  
      b = gcnew Button( );  
      b->Text = "Do Null Access";  
      b->Size = Drawing::Size(150, 30);  
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);  
      Controls->Add(b);  
   }  
   void OnClick(Object^ sender, EventArgs^ args)   
   {  
      // do something illegal, like call through a null pointer...  
      Object^ o = nullptr;  
      o->ToString( );        
   }  
};  
  
ref class App  
{  
public:  
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)  
   {  
      MessageBox::Show(e->Exception->Message, "Global Exeception");  
      Application::ExitThread( );  
   }  
};  
  
int main()  
{  
   Application::ThreadException += gcnew   
      ThreadExceptionEventHandler(App::OnUnhandled);  
  
   MyForm^ form = gcnew MyForm( );  
   Application::Run(form);  
}  
```  
  
## Siehe auch  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)