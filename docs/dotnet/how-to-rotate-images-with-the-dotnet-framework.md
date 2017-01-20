---
title: "Gewusst wie: Drehen von Bildern mit .NET Framework"
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
  - "GDI+ [C++], Drehen von Bildern"
  - "Grafiken [C++], Drehen von Bildern"
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Drehen von Bildern mit .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird die Verwendung der <xref:System.Drawing.Image?displayProperty=fullName>\-Klasse erläutert, um ein Bild von einem Datenträger zu laden, dieses um 90 Grad zu drehen und es als neue JPG\-Datei zu speichern.  
  
> [!NOTE]
>  GDI\+ ist in Windows XP bereits enthalten und steht als verteilbare Komponente für Windows NT 4.0 SP 6, Windows 2000, Windows 98 und Windows Me zur Verfügung.  Um das neueste verteilbare herunterzuladen, wechseln Sie [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Weitere Informationen finden Sie unter [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Beispiel  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );  
   image->Save("SampleImage_rotated.jpg");  
   return 0;  
}  
```  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)