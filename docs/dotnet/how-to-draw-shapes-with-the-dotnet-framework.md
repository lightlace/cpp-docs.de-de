---
title: 'Vorgehensweise: Zeichnen von Formen mit .NET Framework | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 877e78b1ce4f81af76aa20961ea05d18e64f58f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130034"
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>Gewusst wie: Zeichnen von Formen mit .NET Framework
Im folgenden Codebeispiel wird mit der <xref:System.Drawing.Graphics> Klasse so ändern Sie die <xref:System.Windows.Forms.Form.OnPaint%2A> -Ereignishandler, um einen Zeiger zum Abrufen der <xref:System.Drawing.Graphics> Objekt für das Hauptformular. This-Zeiger wird dann verwendet, um die Hintergrundfarbe des Formulars festgelegt und das Zeichnen einer Linie und ein Bogen mit der <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden.  
  
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