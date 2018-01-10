---
title: 'Vorgehensweise: Konvertieren von Bilddateiformaten mit .NET Framework | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dc2b84063c509cd870b5d02fa0a209b511d8a0f3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>Gewusst wie: Konvertieren von Bilddateiformaten mit .NET Framework
Im folgenden Codebeispiel wird veranschaulicht, die <xref:System.Drawing.Image?displayProperty=fullName> Klasse und die <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> Enumeration zum Konvertieren und Speichern von Abbilddateien verwendet. Der folgende Code lädt ein Bild aus einer JPG-Datei, und klicken Sie dann im GIF- und BMP-Dateiformat gespeichert.  
  
> [!NOTE]
>  GDI + ist in Windows XP, Windows Server 2003 und Windows Vista enthalten und ist als verteilbare Komponente für Windows 2000 verfügbar. Informationen zum Herunterladen des neuesten verteilbaren Pakets finden Sie unter [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232).   
  
## <a name="example"></a>Beispiel  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing>   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)