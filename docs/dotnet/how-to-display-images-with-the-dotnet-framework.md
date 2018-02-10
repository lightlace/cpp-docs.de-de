---
title: 'Vorgehensweise: Anzeigen von Bildern mit .NET Framework | Microsoft Docs'
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
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f50659832e04c3b8938c50bedc47b3ac770a52eb
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>Gewusst wie: Anzeigen von Bildern mit .NET Framework
Im folgenden Codebeispiel wird, ändert den OnPaint-Ereignishandler zum Abrufen von eines Zeigers auf die <xref:System.Drawing.Graphics> Objekt für das Hauptformular. Die <xref:System.Windows.Forms.Form.OnPaint%2A> Funktion richtet sich Windows Forms-Anwendung, die wahrscheinlich mit einem Visual Studio-Anwendungs-Assistenten erstellt.  
  
 Das Bild wird dargestellt, indem die <xref:System.Drawing.Image> Klasse. Die Bilddaten werden geladen, aus einer JPG-Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> Methode. Bevor Sie das Bild in der Form gezeichnet wird, wird die Formulargröße an Bild anpassen. Das Zeichnen des Bilds wird ausgeführt, mit der <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> Methode.  
  
 Die <xref:System.Drawing.Graphics> und <xref:System.Drawing.Image> Klassen befinden sich beide im die <xref:System.Drawing?displayProperty=fullName> Namespace.  
  
## <a name="example"></a>Beispiel  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing?displayProperty=fullName>   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)