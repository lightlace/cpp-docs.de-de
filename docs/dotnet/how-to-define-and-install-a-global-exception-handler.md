---
title: 'Vorgehensweise: Definieren und Installieren eines globalen Ausnahmehandlers'
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: d1b8452d19172bf16817c36032189accfd855539
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387395"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>Vorgehensweise: Definieren und Installieren eines globalen Ausnahmehandlers

Im folgenden Codebeispiel wird veranschaulicht, wie nicht behandelte Ausnahmen erfasst werden können. Das Beispielformular enthält eine Schaltfläche, wenn gedrückt, wird einen null-Verweis, dass eine Ausnahme ausgelöst werden. Diese Funktion stellt einen typischen Code Fehler dar. Die resultierende Ausnahme wird vom installiert, indem Sie die main-Funktion anwendungsweiter Ausnahmehandler abgefangen.

Dies erfolgt durch Binden eines Delegaten, der <xref:System.Windows.Forms.Application.ThreadException> Ereignis. Nachfolgende Ausnahmen werden in diesem Fall dann gesendet, um die `App::OnUnhandled` Methode.

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

[Ausnahmebehandlung](../extensions/exception-handling-cpp-component-extensions.md)
