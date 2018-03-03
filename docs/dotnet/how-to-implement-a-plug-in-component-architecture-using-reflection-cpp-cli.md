---
title: Implementieren eine Plug-in-Architektur (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- plug-ins [C++]
- reflection [C++}, plug-ins
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 05c6c2584e39ed145a30c919ed850aac45905a85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-implement-a-plug-in-component-architecture-using-reflection-ccli"></a>Gewusst wie: Implementieren einer Plug-In-Komponentenarchitektur mit Reflektion (C++/CLI)
Die folgenden Codebeispiele veranschaulichen die Verwendung von Reflektion, um eine einfache "-Plug-in" Architektur zu implementieren. Das erste Codelisting ist der Anwendung, und die zweite ist das plug-in. Die Anwendung ist ein mehrere Dokumentformular, das sich über alle formularbasierten Klassen finden in der Plug-in-DLL als Befehlszeilenargument füllt.  
  
 Die Anwendung versucht, das Laden der bereitgestellten Assembly mithilfe der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> Methode. Wenn erfolgreich, die Typen in der Assembly aufgelistet werden mithilfe der <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> Methode. Jeder Typ wird dann für die Verwendung von Kompatibilität überprüft die <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> Methode. In diesem Beispiel wird die in der bereitgestellten Assembly gefundene Klassen abgeleitet werden, aus der <xref:System.Windows.Forms.Form> Klasse als ein plug-in zu qualifizieren.  
  
 Kompatible Klassen werden dann instanziiert, mit der <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> -Methode, die akzeptiert eine <xref:System.Type> als Argument und gibt einen Zeiger auf eine neue Instanz. Jede neue Instanz wird dann in das Formular angefügt und angezeigt.  
  
 Beachten Sie, dass die <xref:System.Reflection.Assembly.Load%2A> Methode akzeptiert keine Assemblynamen, die die Dateierweiterung enthalten. Die main-Funktion in der Anwendung kürzt alle bereitgestellten Erweiterungen aus, damit im folgenden Codebeispiel wird in beiden Fällen funktioniert.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code definiert die Anwendung, die Plug-Ins akzeptiert. Ein Assemblyname muss als erstes Argument angegeben werden. Diese Assembly sollte über mindestens einen öffentlichen enthalten <xref:System.Windows.Forms.Form> abgeleiteten Typ.  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code definiert drei von abgeleitete Klassen <xref:System.Windows.Forms.Form>. Wenn der Name des der resultierende Assemblyname mit der ausführbaren Datei in der vorherigen Liste übergeben wird, wird jede dieser drei Klassen ermittelt und instanziiert, trotz der Tatsache, dass der Host-Anwendung zum Zeitpunkt der Kompilierung nicht bekannt waren.  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)