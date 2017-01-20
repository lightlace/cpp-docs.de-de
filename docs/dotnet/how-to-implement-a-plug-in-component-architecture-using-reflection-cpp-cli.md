---
title: "Gewusst wie: Implementieren einer Plug-In-Komponentenarchitektur mit Reflektion (C++/CLI)"
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
  - "Plug-Ins [C++]"
  - "Reflektion [C++}, Plug-Ins"
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Implementieren einer Plug-In-Komponentenarchitektur mit Reflektion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den folgenden Codebeispielen wird die Verwendung der Reflektion zur Implementierung einer einfachen "Plug\-In"\-Architektur dargestellt.  Zuerst ist die Anwendung aufgeführt, als zweites das Plug\-In.  Bei der Anwendung handelt es sich um ein aus mehreren Dokumenten bestehendes Formular, das über die formularbasierten Klassen der Plug\-In\-DLL ausgefüllt wird, die als Befehlszeilenargument verwendet wird.  
  
 Die Anwendung versucht, die vorliegende Assembly mit der <xref:System.Reflection.Assembly.Load*?displayProperty=fullName>\-Methode zu laden.  Wenn dies erfolgreich ist, werden die Typen in der Assembly mit der <xref:System.Reflection.Assembly.GetTypes*?displayProperty=fullName>\-Methode aufgelistet.  Jeder Typ wird dann mit der <xref:System.Type.IsAssignableFrom*?displayProperty=fullName>\-Methode auf Kompatibilität überprüft.  In diesem Beispiel müssen die in der vorliegenden Assembly vorhandenen Klassen aus der <xref:System.Windows.Forms.Form>\-Klasse abgeleitet werden, um als Plug\-In behandelt werden zu können.  
  
 Kompatible Klassen werden dann mit der <xref:System.Activator.CreateInstance*?displayProperty=fullName>\-Methode instanziiert, die <xref:System.Type> als Argument akzeptiert und einen Zeiger auf eine neue Instanz zurückgibt.  Jede neue Instanz wird anschließend an das Formular angefügt und angezeigt.  
  
 Beachten Sie, dass die <xref:System.Reflection.Assembly.Load*>\-Methode keine Assemblynamen akzeptiert, die die Dateierweiterung einschließen.  Alle vorhandenen Erweiterungen werden von der Hauptfunktion der Anwendung entfernt, daher funktioniert das folgende Codebeispiel in beiden Fällen.  
  
## Beispiel  
 Der folgende Code definiert die Anwendung, die Plug\-Ins akzeptiert.  Als erstes Argument muss ein Assemblyname angegeben werden.  Diese Assembly sollte mindestens einen öffentlichen, von <xref:System.Windows.Forms.Form> abgeleiteten Typ enthalten.  
  
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
  
## Beispiel  
 Im folgenden Code werden drei von <xref:System.Windows.Forms.Form> abgeleitete Klassen definiert.  Bei der Übergabe des Namens der resultierenden Assembly an den ausführbaren Code im ersten Teil werden diese drei Klassen gefunden und instanziiert, obwohl sie der Hosting\-Anwendung zur Kompilierungszeit nicht bekannt waren.  
  
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
  
## Siehe auch  
 [Reflektion](../dotnet/reflection-cpp-cli.md)