---
title: 'Vorgehensweise: definieren und installieren ein globalen Ausnahmehandlers | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff91a742b1a6641fbc689968587f0472c333e16a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423356"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>Gewusst wie: Definieren und Installieren eines globalen Ausnahmehandlers

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

[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)