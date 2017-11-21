---
title: 'Vorgehensweise: Zeichnen von Formen mit .NET Framework | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9c9c2fedb4bb07fa2301368e4bd7b62fb636d3fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>Gewusst wie: Zeichnen von Formen mit .NET Framework
Im folgenden Codebeispiel wird mit der <xref:System.Drawing.Graphics> Klasse so ändern Sie die <xref:System.Windows.Forms.Form.OnPaint%2A> -Ereignishandler, um einen Zeiger zum Abrufen der <xref:System.Drawing.Graphics> Objekt für das Hauptformular. This-Zeiger wird dann verwendet, um die Hintergrundfarbe des Formulars festgelegt und das Zeichnen einer Linie und ein Bogen mit der <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden.  
  
> [!NOTE]
>  GDI + ist in Windows XP enthalten und ist als verteilbare Komponente für Windows NT 4.0 SP 6, Windows 2000, Windows 98 und WindowsMe verfügbar. Informationen zum Herunterladen des neuesten verteilbaren Pakets finden Sie unter [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232). 
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [.NET Programmieren mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing-namespace](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)