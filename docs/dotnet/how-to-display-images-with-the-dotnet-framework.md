---
title: "Gewusst wie: Anzeigen von Bildern mit .NET Framework"
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
  - "GDI+ [C++], Anzeigen von Bildern"
  - "Grafiken [C++], Anzeigen von Bildern"
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Anzeigen von Bildern mit .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird der OnPaint\-Ereignishandler geändert, um einen Zeiger auf das <xref:System.Drawing.Graphics>\-Objekt des Hauptformulars zu erhalten.  Die <xref:System.Windows.Forms.Form.OnPaint*>\-Funktion ist für eine Windows Forms\-Anwendung vorgesehen, die üblicherweise mit einem Anwendungs\-Assistenten in Visual Studio erstellt wird.  
  
 Das Bild wird durch die <xref:System.Drawing.Image>\-Klasse dargestellt.  Die Bilddaten werden mit der <xref:System.Drawing.Image.FromFile*?displayProperty=fullName>\-Methode aus einer JPG\-Datei geladen.  Bevor das Bild in das Formular gezeichnet wird, wird die Formulargröße an die Bildgröße angepasst.  Das Zeichnen des Bildes erfolgt mithilfe der <xref:System.Drawing.Graphics.DrawImage*?displayProperty=fullName>\-Methode.  
  
 Die <xref:System.Drawing.Graphics>\-Klasse und die <xref:System.Drawing.Image>\-Klasse befinden sich im <xref:System.Drawing?displayProperty=fullName>\-Namespace.  
  
> [!NOTE]
>  GDI\+ ist in Windows XP bereits enthalten und steht als verteilbare Komponente für Windows NT 4.0 SP 6, Windows 2000, Windows 98 und Windows Millennium Edition zur Verfügung.  Um das neueste verteilbare herunterzuladen, wechseln Sie [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Weitere Informationen finden Sie in der Dokumentation zum GDI\+\-SDK unter [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Beispiel  
  
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
  
## Siehe auch  
 <xref:System.Drawing?displayProperty=fullName>   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)