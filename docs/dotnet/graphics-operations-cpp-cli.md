---
title: Grafikoperationen (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: dd27fc603454d18f30fb367399e0ee18be74015e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505429"
---
# <a name="graphics-operations-ccli"></a>Grafikoperationen (C++/CLI)

Zeigt die Bildmanipulation mithilfe des Windows SDK.

In den folgenden Themen wird die Verwendung der <xref:System.Drawing.Image?displayProperty=fullName>-Klasse für die Bildmanipulation dargestellt.

## <a name="display"></a> Anzeigen von Bildern mit .NET Framework

Das folgende Codebeispiel ändert den OnPaint-Ereignishandler zum Abrufen der eines Zeigers auf die <xref:System.Drawing.Graphics> Objekt für das Hauptformular. Die <xref:System.Windows.Forms.Form.OnPaint%2A> Funktion richtet eine Windows Forms-Anwendung in den meisten Fällen mit einem Visual Studio-Anwendungs-Assistenten erstellt.

Das Bild wird dargestellt, durch die <xref:System.Drawing.Image> Klasse. Laden der Image-Daten aus einer JPG-Datei mit den <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> Methode. Bevor das Bild in der Form gezeichnet wird, wird die Formulargröße an das Bild angepasst. Das Zeichnen des Bilds wird ausgeführt, mit der <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> Methode.

Die <xref:System.Drawing.Graphics> und <xref:System.Drawing.Image> Klassen sind in der <xref:System.Drawing?displayProperty=fullName> Namespace.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="draw"></a> Zeichnen von Formen mit .NET Framework

Im folgenden Codebeispiel wird die <xref:System.Drawing.Graphics> Klasse so ändern Sie die <xref:System.Windows.Forms.Form.OnPaint%2A> -Ereignishandler zum Abrufen der eines Zeigers auf die <xref:System.Drawing.Graphics> Objekt für das Hauptformular. This-Zeiger wird dann zum Festlegen der Hintergrundfarbe des Formulars und Zeichnen einer Linie und einen Bogen mithilfe der <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> und <xref:System.Drawing.Graphics.DrawArc%2A> Methoden.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="rotate"></a> Drehen von Bildern mit .NET Framework

Das folgende Codebeispiel veranschaulicht die Verwendung von der <xref:System.Drawing.Image?displayProperty=fullName> -Klasse zum Laden eines Bilds vom Datenträger, um 90 Grad drehen, und speichern Sie sie als neue JPG-Datei.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="convert"></a> Konvertieren von Bilddateiformaten mit .NET Framework

Im folgenden Codebeispiel wird veranschaulicht, die <xref:System.Drawing.Image?displayProperty=fullName> Klasse und die <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> Enumeration, die zum Konvertieren und Speichern von Bilddateien verwendet. Der folgende Code lädt ein Bild aus einer JPG-Datei, und klicken Sie dann im GIF und BMP-Datei-Format gespeichert.

### <a name="example"></a>Beispiel

```cpp
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

## <a name="related-sections"></a>Verwandte Abschnitte

[Erste Schritte mit Grafikprogrammierung](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[Verwalteter Code in GDI+](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
