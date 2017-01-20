---
title: "Gewusst wie: Zeichnen von Formen mit .NET Framework"
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
  - "Zeichnung, Formen"
  - "GDI+, Zeichnen von Formen"
  - "Formen"
  - "Formen, Zeichnung"
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Zeichnen von Formen mit .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die <xref:System.Drawing.Graphics>\-Klasse verwendet, um den <xref:System.Windows.Forms.Form.OnPaint*>\-Ereignishandler zu ändern. Dadurch wird ein Zeiger auf das <xref:System.Drawing.Graphics>\-Objekt für das Hauptformular abgerufen.  Mit diesem Zeiger wird anschließend die Hintergrundfarbe des Formulars festgelegt und mit der <xref:System.Drawing.Graphics.DrawLine*?displayProperty=fullName>\-Methode und der <xref:System.Drawing.Graphics.DrawArc*>\-Methode eine Linie und ein Bogen gezeichnet.  
  
> [!NOTE]
>  GDI\+ ist in Windows XP bereits enthalten und steht als verteilbare Komponente für Windows NT 4.0 SP 6, Windows 2000, Windows 98 und Windows Millennium Edition zur Verfügung.  Um das neueste verteilbare herunterzuladen, wechseln Sie [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Weitere Informationen finden Sie unter [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Beispiel  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing\-Namespace](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)