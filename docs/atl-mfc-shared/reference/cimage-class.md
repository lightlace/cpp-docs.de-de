---
title: "CImage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CImage"
  - "ATL.CImage"
  - "ATL::CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".gif-Dateien, ATL and MFC support"
  - "Bitmaps [C++], ATL and MFC support for"
  - "CImage class"
  - "GIF-Dateien, ATL and MFC support"
  - "Bilder [C++], ATL and MFC support for"
  - "JPEG-Dateien"
  - "PNG-Dateien, ATL and MFC support"
  - "transparent color"
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CImage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CImage` bietet verbesserte Bit\-Übersichtsunterstützung, einschließlich der Möglichkeit, Bilder, JPEG\-, GIF\- und PNG\-Dateien in Stilen des Portablen Network Graphics \(PNG\) zu laden und zu speichern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CImage  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::CImage](../Topic/CImage::CImage.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md)|Zeigt Bitmaps an, die die transparenten oder halbtransparenten Pixel haben.|  
|[CImage::Attach](../Topic/CImage::Attach.md)|Fügt `HBITMAP` zu einem `CImage`\-Objekt.  Kann mit Bitmap\- oder DIB\-Abschnittsbitmaps des Abschnitts verwendet werden entweder NichtDIB.|  
|[CImage::BitBlt](../Topic/CImage::BitBlt.md)|Kopiert eine Bitmap vom Quellgerätekontext zu diesem aktuellen Gerätekontext.|  
|[CImage::Create](../Topic/CImage::Create.md)|Erstellt eine und fügt sie DIB\-Abschnittsbitmap zum zuvor erstellten `CImage`\-Objekt.|  
|[CImage::CreateEx](../Topic/CImage::CreateEx.md)|Stellt eine DIB\-Abschnittsbitmap \(mit zusätzlichen Parameter\) und fügt es dem zuvor erstellten `CImage`\-Objekt.|  
|[CImage::Destroy](../Topic/CImage::Destroy.md)|Trennt die Bitmap aus dem `CImage`\-Objekt und zerstört die Bitmap.|  
|[CImage::Detach](../Topic/CImage::Detach.md)|Trennt die Bitmap aus einem `CImage`\-Objekt.|  
|[CImage::Draw](../Topic/CImage::Draw.md)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck.  **Draw** oder komprimiert wird die Bitmap, um die Dimensionen des Zielrechtecks ggf. angepasst und behandelt Alphablending und transparente Farben.|  
|[CImage::GetBits](../Topic/CImage::GetBits.md)|Ruft einen Zeiger auf den tatsächlichen Pixelwerten der Bitmap ab.|  
|[CImage::GetBPP](../Topic/CImage::GetBPP.md)|Ruft die Bits pro Pixel ab.|  
|[CImage::GetColorTable](../Topic/CImage::GetColorTable.md)|Ruft die Rot, Grün, Blau Farbwerte \(RGB\) von einem Bereich von Einträgen in der Farbtabelle ab.|  
|[CImage::GetDC](../Topic/CImage::GetDC.md)|Ruft den Gerätekontext ab, in den die aktuelle Bitmap ausgewählt ist.|  
|[CImage::GetExporterFilterString](../Topic/CImage::GetExporterFilterString.md)|Sucht die verfügbaren Bildformate und ihre Beschreibungen.|  
|[CImage::GetHeight](../Topic/CImage::GetHeight.md)|Ruft die Höhe des aktuellen Bilder in Pixel ab.|  
|[CImage::GetImporterFilterString](../Topic/CImage::GetImporterFilterString.md)|Sucht die verfügbaren Bildformate und ihre Beschreibungen.|  
|[CImage::GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)|Ruft die maximale Anzahl von Einträgen in der Farbtabelle ab.|  
|[CImage::GetPitch](../Topic/CImage::GetPitch.md)|Ruft die Schriftbreite des aktuellen Bilder in Bytes ab.|  
|[CImage::GetPixel](../Topic/CImage::GetPixel.md)|Ruft die Farbe des Pixels ab, das von *x* and *y* angegeben wird.|  
|[CImage::GetPixelAddress](../Topic/CImage::GetPixelAddress.md)|Ruft die Adresse eines bestimmten Pixels ab.|  
|[CImage::GetTransparentColor](../Topic/CImage::GetTransparentColor.md)|Ruft die Position der transparente Farbe in der Farbtabelle ab.|  
|[CImage::GetWidth](../Topic/CImage::GetWidth.md)|Ruft die Breite des aktuellen Bilder in Pixel ab.|  
|[CImage::IsDIBSection](../Topic/CImage::IsDIBSection.md)|Bestimmt, ob die angefügte Bitmap ein DIB\-Abschnitt ist.|  
|[CImage::IsIndexed](../Topic/CImage::IsIndexed.md)|Gibt an, dass die Farben einer Bitmap auf einer indizierten Palette zugeordnet werden.|  
|[CImage::IsNull](../Topic/CImage::IsNull.md)|Gibt an, ob eine Quellbitmap derzeit geladen wird.|  
|[CImage::IsTransparencySupported](../Topic/CImage::IsTransparencySupported.md)|Gibt an, ob die Anwendung, transparente Bitmaps unterstützt und wurde für Windows 2000 oder höher kompiliert.|  
|[CImage::Load](../Topic/CImage::Load.md)|Lädt ein Bild aus der angegebenen Datei.|  
|[CImage::LoadFromResource](../Topic/CImage::LoadFromResource.md)|Lädt ein Bild aus der angegebenen Ressource.|  
|[CImage::MaskBlt](../Topic/CImage::MaskBlt.md)|Kombiniert die Farbdaten für die Quell\- und Zielbitmaps mithilfe des angegebenen Masken\- und Rastervorgangs.|  
|[CImage::PlgBlt](../Topic/CImage::PlgBlt.md)|Führt einen Bitblocktransfer aus einem Rechteck in einem Quellgerätekontext in ein Parallelogramm in einem Zielgerätekontext aus.|  
|[CImage::ReleaseDC](../Topic/CImage::ReleaseDC.md)|Gibt den Gerätekontext frei, der mit [CImage::GetDC](../Topic/CImage::GetDC.md) abgerufen wurde.|  
|[CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)|Gibt die Ressourcen frei, die von GDI\+ verwendet werden.  Muss um Ressourcen Mittel aufgerufen werden, das ein globales `CImage`\-Objekt erstellt wird.|  
|[CImage::Save](../Topic/CImage::Save.md)|Speichert ein Bild als der angegebene Typ.  **Speichern** kann Imageoptionen nicht angeben.|  
|[CImage::SetColorTable](../Topic/CImage::SetColorTable.md)|Legt rote, Grün, Blau RGB\-\) Farbwerte in einem Bereich von Einträgen in der Farbtabelle der DIB\-Abschnitts fest.|  
|[CImage::SetPixel](../Topic/CImage::SetPixel.md)|Legt das Pixel an angegebenen Koordinaten der angegebenen Farbe fest.|  
|[CImage::SetPixelIndexed](../Topic/CImage::SetPixelIndexed.md)|Legt das Pixel an angegebenen Koordinaten die Farbe am angegebenen Index der Palette fest.|  
|[CImage::SetPixelRGB](../Topic/CImage::SetPixelRGB.md)|Legt das Pixel an angegebenen Koordinaten zum angegebenen Rot, Grün, Blau Wert \(RGB\) fest.|  
|[CImage::SetTransparentColor](../Topic/CImage::SetTransparentColor.md)|Legt den behandelt werden Index der Farbe, fest, wie transparent.  Nur eine Farbe in einer Palette kann transparent sein.|  
|[CImage::StretchBlt](../Topic/CImage::StretchBlt.md)|Kopiert eine Bitmap aus einem Quellrechteck in ein Zielrechteck und streckt oder komprimiert die Bitmap, um die Dimensionen des Zielrechtecks an, ggf.|  
|[CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md)|Kopiert eine Bitmap mit transparenter Farbe im Quellgerätekontext zu diesem aktuellen Gerätekontext.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CImage::operator HBITMAP](../Topic/CImage::operator%20HBITMAP.md)|Gibt das Windows\-Handles zurück, das dem Objekt `CImage` angefügt wird.|  
  
## Hinweise  
 `CImage` akzeptiert Bitmaps, die entweder Abschnitte der geräteunabhängige Bitmaps \(DIBs\) oder nicht sind; Sie können jedoch [Erstellen Sie](../Topic/CImage::Create.md) oder [CImage::Load](../Topic/CImage::Load.md) mit nur DIB\-Abschnitten verwenden.  Sie können eine Bitmap des Abschnitts NichtDIB zu einem `CImage`\-Objekt mithilfe [Anfügen](../Topic/CImage::Attach.md) anfügen, und dann können Sie die folgenden `CImage` keine Methoden verwenden, die nur DIB\-Abschnittsbitmaps unterstützen:  
  
-   [GetBits](../Topic/CImage::GetBits.md)  
  
-   [GetColorTable](../Topic/CImage::GetColorTable.md)  
  
-   [GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)  
  
-   [GetPitch](../Topic/CImage::GetPitch.md)  
  
-   [GetPixelAddress](../Topic/CImage::GetPixelAddress.md)  
  
-   [IsIndexed](../Topic/CImage::IsIndexed.md)  
  
-   [SetColorTable](../Topic/CImage::SetColorTable.md)  
  
 Um festzustellen wenn eine angefügte Bitmap ein DIB\-Abschnitt ist, rufen Sie [IsDibSection](../Topic/CImage::IsDIBSection.md)**.** auf  
  
> [!NOTE]
>  **Hinweis**  in Visual Studio .NET 2003., diese Klasse enthält die Anzahl der `CImage`\-Objekte erstellt.  Sobald die Anzahl auf 0 ansteigt, wird die Funktion [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) automatisch aufgerufen, um die Ressourcen freizugeben, die von GDI\+ verwendet werden.  Dadurch wird sichergestellt, dass alle `CImage`\-Objekte, die direkt oder indirekt über DLL erstellt werden, immer ordnungsgemäß gelöscht werden und dass **GdiplusShutdown** nicht von `DllMain` aufgerufen wird.  
  
> [!NOTE]
>  Mit globalen `CImage` wird Objekte in einer DLL nicht empfohlen.  Wenn Sie ein globales Objekt `CImage` in einer DLL verwenden müssen, verwendete Aufruf [CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md), um von Ressourcen explizit freizugeben von GDI\+.  
  
 `CImage` kann nicht in neues [CDC](../../mfc/reference/cdc-class.md) ausgewählt werden.  `CImage` erstellt sein eigenes **HDC** für das Bild.  Da `HBITMAP` in ein **HDC** nur ausgewählt werden kann, kann `HBITMAP`, das mit `CImage` zugeordnet ist, nicht in ein anderes **HDC** ausgewählt werden.  Wenn Sie `CDC` benötigen, rufen Sie **HDC** von `CImage` ab und geben Sie es [CDC::FromHandle](../Topic/CDC::FromHandle.md).  
  
## Beispiel  
 [!CODE [NVC_ATLMFC_Utilities#70](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#70)]  
  
 Wenn Sie `CImage` in einem MFC\-Projekt verwenden, beachten Sie, dem Memberfunktionen im Projekt einen Zeiger auf ein Objekt [CBitmap](../../mfc/reference/cbitmap-class.md) erwarten.  Wenn Sie `CImage` mit solchen Features, z [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md), verwendet [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md) verwenden, es führen das `CImage``HBITMAP`, und zurückgegebene `CBitmap*` verwenden möchten.  
  
## Beispiel  
 [!CODE [NVC_ATLMFC_Utilities#71](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#71)]  
  
 Durch `CImage` haben Sie Zugriff auf den tatsächlichen Bits eines DIB\-Abschnitts.  Sie können ein Objekt `CImage` verwenden, überall, das Sie zuvor Win32 HBITMAP oder DIB\-Abschnitt haben.  
  
> [!NOTE]
>  Die folgenden `CImage`\-Methoden haben Einschränkungen für ihre Verwendung:  
  
|Methode|Einschränkung|  
|-------------|-------------------|  
|[PlgBlt](../Topic/CImage::PlgBlt.md)|Kann mit nur Windows NT 4.0 oder höher.  Nicht an Anwendungen funktioniert das Ausführen auf Windows 95\/98 oder höher.|  
|[MaskBlt](../Topic/CImage::MaskBlt.md)|Kann mit nur Windows NT 4.0 oder höher.  Nicht an Anwendungen funktioniert das Ausführen auf Windows 95\/98 oder höher.|  
|[AlphaBlend](../Topic/CImage::AlphaBlend.md)|Kann mit nur Windows 2000, Windows 98 und höheren Systemen.|  
|[TransparentBlt](../Topic/CImage::TransparentBlt.md)|Kann mit nur Windows 2000, Windows 98 und höheren Systemen.|  
|[Zeichnen Sie](../Topic/CImage::Draw.md)|Unterstützt Transparenz nur mit Windows 2000, Windows 98 und höheren Systemen.|  
  
 Siehe [CImage\-Einschränkungen mit älteren Betriebssystemen](../../mfc/cimage-limitations-with-earlier-operating-systems.md) für ausführlichere Informationen über die Einschränkungen für diesen Methoden.  
  
 Sie können `CImage` entweder von MFC oder ATL von verwenden.  
  
> [!NOTE]
>  Wenn Sie ein Projekt mit `CImage` erstellen, müssen Sie `CString` definieren, bevor Sie `atlimage.h` einschließen.  Wenn das Projekt ATL ohne MFC verwendet, Include\- `atlstr.h`, bevor Sie `atlimage.h` einschließen.  Wenn das Projekt \(MFC verwendet, oder wenn es ein ATL\-Projekt mit MFC\-Unterstützung ist\), Include\- `afxstr.h`, bevor Sie `atlimage.h` einschließen.  
>   
>  Ebenso müssen Sie `atlimage.h` einschließen, bevor Sie `atlimpl.cpp` einschließen.  Um dieses leicht zu erreichen, schließen Sie `atlimage.h` im `stdafx.h` ein.  
  
## Anforderungen  
 **Header:**  atlimage.h  
  
## Siehe auch  
 [MMXSwarm\-Beispiel](../../top/visual-cpp-samples.md)   
 [SimpleImage\-Beispiel](../../top/visual-cpp-samples.md)   
 [Device\-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)