---
title: 'Vorgehensweise: Anzeigen von Bildern mit .NET Framework | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 23e8445e5a407e71061a971bccfb77d6b4170a35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-display-images-with-the-net-framework"></a>Gewusst wie: Anzeigen von Bildern mit .NET Framework
Im folgenden Codebeispiel wird, ändert den OnPaint-Ereignishandler zum Abrufen von eines Zeigers auf die <xref:System.Drawing.Graphics> Objekt für das Hauptformular. Die <xref:System.Windows.Forms.Form.OnPaint%2A> Funktion richtet sich Windows Forms-Anwendung, die wahrscheinlich mit einem Visual Studio-Anwendungs-Assistenten erstellt.  
  
 Das Bild wird dargestellt, indem die <xref:System.Drawing.Image> Klasse. Die Bilddaten werden geladen, aus einer JPG-Datei mithilfe der <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> Methode. Bevor Sie das Bild in der Form gezeichnet wird, wird die Formulargröße an Bild anpassen. Das Zeichnen des Bilds wird ausgeführt, mit der <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> Methode.  
  
 Die <xref:System.Drawing.Graphics> und <xref:System.Drawing.Image> Klassen befinden sich beide im die <xref:System.Drawing?displayProperty=fullName> Namespace.  
  
> [!NOTE]
>  GDI + ist in Windows XP enthalten und ist als verteilbare Komponente für Windows NT 4.0 SP 6, Windows 2000, Windows 98 und WindowsMe verfügbar. Informationen zum Herunterladen des neuesten verteilbaren Pakets finden Sie unter [http://go.microsoft.com/fwlink/?linkid=11232](http://go.microsoft.com/fwlink/?linkid=11232).   
  
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