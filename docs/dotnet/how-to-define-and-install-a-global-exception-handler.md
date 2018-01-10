---
title: 'Vorgehensweise: definieren und installieren ein globalen Ausnahmehandlers | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1d9b1125fc54ecbd75fc49b36498a99f5e86f28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>Gewusst wie: Definieren und Installieren eines globalen Ausnahmehandlers
Im folgenden Codebeispiel wird veranschaulicht, wie nicht behandelte Ausnahmen erfasst werden können. Das Beispielformular eine Schaltfläche enthält, wenn gedrückt wird, führt einen null-Verweis, verursacht eine Ausnahme ausgelöst werden. Diese Funktion stellt einen typische Code Fehler dar. Die resultierende Ausnahme wird vom installiert, indem Sie die main-Funktion eine anwendungsweite Ausnahmehandler abgefangen.  
  
 Dies wird erreicht, indem das Binden eines Delegaten an die <xref:System.Windows.Forms.Application.ThreadException> Ereignis. Nachfolgende Ausnahmen werden in diesem Fall dann gesendet, um die `App::OnUnhandled` Methode.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)