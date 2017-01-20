---
title: "CMFCToolBarImages Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarImages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarImages class"
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
caps.handback.revision: "19"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarImages Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Bilder auf einer Symbolleiste.  Die `CMFCToolBarImages`\-Klasse verwaltet die Symbolleistenimages, die aus Anwendungsressourcen oder aus Dateien geladen werden.  
  
## Syntax  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](../Topic/CMFCToolBarImages::CMFCToolBarImages.md)|Erstellt ein `CMFCToolBarImages`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](../Topic/CMFCToolBarImages::AdaptColors.md)||  
|[CMFCToolBarImages::AddIcon](../Topic/CMFCToolBarImages::AddIcon.md)|Fügt ein Symbol den Symbolleistenimages hinzu.|  
|[CMFCToolBarImages::AddImage](../Topic/CMFCToolBarImages::AddImage.md)|Fügt eine Bitmap den Symbolleistenimages hinzu.|  
|[CMFCToolBarImages::CleanUp](../Topic/CMFCToolBarImages::CleanUp.md)||  
|[CMFCToolBarImages::Clear](../Topic/CMFCToolBarImages::Clear.md)|Gibt die Systemressourcen frei, die diesem Objekt zugeordnet wurden.|  
|[CMFCToolBarImages::ConvertTo32Bits](../Topic/CMFCToolBarImages::ConvertTo32Bits.md)|Wird unterstrichen Bitmap auf 32 bpp Bilder.|  
|[CMFCToolBarImages::CopyImageToClipboard](../Topic/CMFCToolBarImages::CopyImageToClipboard.md)||  
|[CMFCToolBarImages::CopyTo](../Topic/CMFCToolBarImages::CopyTo.md)||  
|[CMFCToolBarImages::CreateFromImageList](../Topic/CMFCToolBarImages::CreateFromImageList.md)|Initialisiert die Symbolleistenimages aus einer Bildliste \([CImageList Class](../../mfc/reference/cimagelist-class.md)\).|  
|[CMFCToolBarImages::CreateRegionFromImage](../Topic/CMFCToolBarImages::CreateRegionFromImage.md)||  
|[CMFCToolBarImages::DeleteImage](../Topic/CMFCToolBarImages::DeleteImage.md)|Löscht das Bild, das einen angegebenen Index aus der Symbolleistenimages verfügt, wenn dieser Satz Symbolleistenimages benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::Draw](../Topic/CMFCToolBarImages::Draw.md)|Zeichnet ein einzelnes Symbolleistenbild \(Schaltfläche\).|  
|[CMFCToolBarImages::DrawEx](../Topic/CMFCToolBarImages::DrawEx.md)||  
|[CMFCToolBarImages::EnableRTL](../Topic/CMFCToolBarImages::EnableRTL.md)||  
|[CMFCToolBarImages::EndDrawImage](../Topic/CMFCToolBarImages::EndDrawImage.md)|Gibt Systemressourcen frei, nachdem ein Symbolleistenbild gezeichnet wird.|  
|[CMFCToolBarImages::ExtractIcon](../Topic/CMFCToolBarImages::ExtractIcon.md)|Gibt das Symbol zurück, das einen angegebenen Bildindex von den Symbolleistenimages verfügt.|  
|[CMFCToolBarImages::FillDitheredRect](../Topic/CMFCToolBarImages::FillDitheredRect.md)|Füllt ein Rechteck mit einem Pinsel aus, der die Symbolleistenhintergrundfarben verfügt.|  
|[CMFCToolBarImages::GetAlwaysLight](../Topic/CMFCToolBarImages::GetAlwaysLight.md)||  
|[CMFCToolBarImages::GetBitsPerPixel](../Topic/CMFCToolBarImages::GetBitsPerPixel.md)|Gibt aktuelle Auflösung von unterstrichenen Bilder zurück.|  
|[CMFCToolBarImages::GetCount](../Topic/CMFCToolBarImages::GetCount.md)|Gibt die Anzahl der Bilder auf der Symbolleiste zurück.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](../Topic/CMFCToolBarImages::GetDisabledImageAlpha.md)|Gibt den Alphakanalwert zurück, der für deaktivierte Bilder verwendet wird.|  
|[CMFCToolBarImages::GetFadedImageAlpha](../Topic/CMFCToolBarImages::GetFadedImageAlpha.md)||  
|[CMFCToolBarImages::GetImageSize](../Topic/CMFCToolBarImages::GetImageSize.md)|Ruft entweder die Größe der Symbolleistenimages ab, die im Arbeitsspeicher \(Quellgröße\) gespeichert werden, oder die Größe der Symbolleistenimages, die auf dem Bildschirm gezeichnet werden \(Zielgröße\).|  
|[CMFCToolBarImages::GetImageWell](../Topic/CMFCToolBarImages::GetImageWell.md)|Gibt das Handle auf die Bitmap zurück, die alle Symbolleistenimages enthält.|  
|[CMFCToolBarImages::GetImageWellLight](../Topic/CMFCToolBarImages::GetImageWellLight.md)||  
|[CMFCToolBarImages::GetLastImageRect](../Topic/CMFCToolBarImages::GetLastImageRect.md)||  
|[CMFCToolBarImages::GetLightPercentage](../Topic/CMFCToolBarImages::GetLightPercentage.md)||  
|[CMFCToolBarImages::GetMapTo3DColors](../Topic/CMFCToolBarImages::GetMapTo3DColors.md)||  
|[CMFCToolBarImages::GetMask](../Topic/CMFCToolBarImages::GetMask.md)||  
|[CMFCToolBarImages::GetResourceOffset](../Topic/CMFCToolBarImages::GetResourceOffset.md)|Gibt den Bildindex für eine bestimmte Ressourcen\-ID zurück|  
|[CMFCToolBarImages::GetScale](../Topic/CMFCToolBarImages::GetScale.md)|Aktuelles Skala\-Verhältnis der EINGABETASTE unterstrichene Bilder.|  
|[CMFCToolBarImages::GetTransparentColor](../Topic/CMFCToolBarImages::GetTransparentColor.md)||  
|[CMFCToolBarImages::GrayImages](../Topic/CMFCToolBarImages::GrayImages.md)|Blendet die Symbolleistenimages ab, um den deaktivierten Aussehen zu ihnen.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](../Topic/CMFCToolBarImages::Is32BitTransparencySupported.md)|Bestimmt, ob das Betriebssystem 32\-Bit\-Alphablending unterstützt.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](../Topic/CMFCToolBarImages::IsPreMultiplyAutoCheck.md)||  
|[CMFCToolBarImages::IsRTL](../Topic/CMFCToolBarImages::IsRTL.md)|Bestimmt, ob Unterstützung \(RTL\) von rechts nach links aktiviert ist.|  
|[CMFCToolBarImages::IsReadOnly](../Topic/CMFCToolBarImages::IsReadOnly.md)|Bestimmt, ob die Symbolleistenimages schreibgeschützt sind.|  
|[CMFCToolBarImages::IsScaled](../Topic/CMFCToolBarImages::IsScaled.md)|Teilt mit, ob die unterstrichenen Bilder oder nicht skaliert werden.|  
|[CMFCToolBarImages::IsUserImagesList](../Topic/CMFCToolBarImages::IsUserImagesList.md)|Bestimmt, ob dieser Satz Symbolleistenimages benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::IsValid](../Topic/CMFCToolBarImages::IsValid.md)|Bestimmt, ob dieser Satz Symbolleistenimages ein gültiges Symbolleistenbild enthält.|  
|[CMFCToolBarImages::Load](../Topic/CMFCToolBarImages::Load.md)|Lastsymbolleistenimages von Systemressourcen oder aus einer Datei.|  
|[CMFCToolBarImages::LoadStr](../Topic/CMFCToolBarImages::LoadStr.md)||  
|[CMFCToolBarImages::MapFromSysColor](../Topic/CMFCToolBarImages::MapFromSysColor.md)||  
|[CMFCToolBarImages::MapTo3dColors](../Topic/CMFCToolBarImages::MapTo3dColors.md)||  
|[CMFCToolBarImages::MapToSysColor](../Topic/CMFCToolBarImages::MapToSysColor.md)||  
|[CMFCToolBarImages::MapToSysColorAlpha](../Topic/CMFCToolBarImages::MapToSysColorAlpha.md)||  
|[CMFCToolBarImages::Mirror](../Topic/CMFCToolBarImages::Mirror.md)|Spiegelt horizontal alle Symbolleistenimages.|  
|[CMFCToolBarImages::MirrorBitmap](../Topic/CMFCToolBarImages::MirrorBitmap.md)|Spiegelt horizontal eine Bitmap.|  
|[CMFCToolBarImages::MirrorBitmapVert](../Topic/CMFCToolBarImages::MirrorBitmapVert.md)||  
|[CMFCToolBarImages::MirrorVert](../Topic/CMFCToolBarImages::MirrorVert.md)||  
|[CMFCToolBarImages::OnSysColorChange](../Topic/CMFCToolBarImages::OnSysColorChange.md)||  
|[CMFCToolBarImages::PrepareDrawImage](../Topic/CMFCToolBarImages::PrepareDrawImage.md)|Ordnet die Ressourcen zu, die erforderlich sind, um ein Symbolleistenbild an einem angegebenen zu zeichnen.|  
|[CMFCToolBarImages::Save](../Topic/CMFCToolBarImages::Save.md)|Speichert die Symbolleistenimages in einer Datei, wenn dieser Satz Symbolleistenimages benutzerdefinierte Bilder enthält.|  
|[CMFCToolBarImages::SetAlwaysLight](../Topic/CMFCToolBarImages::SetAlwaysLight.md)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](../Topic/CMFCToolBarImages::SetDisabledImageAlpha.md)|Legt den Alphakanalwert fest, der für deaktivierte Bilder verwendet wird.|  
|[CMFCToolBarImages::SetFadedImageAlpha](../Topic/CMFCToolBarImages::SetFadedImageAlpha.md)||  
|[CMFCToolBarImages::SetImageSize](../Topic/CMFCToolBarImages::SetImageSize.md)|Legt die Größe eines Symbolleistenimages fest \(Quellgröße\).|  
|[CMFCToolBarImages::SetLightPercentage](../Topic/CMFCToolBarImages::SetLightPercentage.md)||  
|[CMFCToolBarImages::SetMapTo3DColors](../Topic/CMFCToolBarImages::SetMapTo3DColors.md)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](../Topic/CMFCToolBarImages::SetPreMultiplyAutoCheck.md)||  
|[CMFCToolBarImages::SetSingleImage](../Topic/CMFCToolBarImages::SetSingleImage.md)||  
|[CMFCToolBarImages::SetTransparentColor](../Topic/CMFCToolBarImages::SetTransparentColor.md)|Legt die transparente Farbe der Symbolleistenimages fest.|  
|[CMFCToolBarImages::SmoothResize](../Topic/CMFCToolBarImages::SmoothResize.md)|Ändert reibungslos unterstrichene Bilder Größe.|  
|[CMFCToolBarImages::UpdateImage](../Topic/CMFCToolBarImages::UpdateImage.md)|Aktualisiert ein benutzerdefiniertes Symbolleistenbild einer Bitmap.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](../Topic/CMFCToolBarImages::PreMultiplyAlpha.md)||  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::m\_bDisableTrueColorAlpha](../Topic/CMFCToolBarImages::m_bDisableTrueColorAlpha.md)|`TRUE`, wenn truecolor Alphablending \(32\-Bit\-Farbe\) deaktiviert ist.|  
  
## Hinweise  
 Die vollständige Bitmap aus den Symbolleistenimages, die von `CMFCToolbarImages` verwaltet werden, besteht aus einem oder mehreren kleinen Symbolleistenimages \(Schaltflächen\) einer festen Größe.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CMFCToolBarImages` konfiguriert, indem verschiedene Methoden in der `CMFCToolBarImages`\-Klasse angewendet wird.  Im Beispiel wird gezeigt, wie die Größe des Symbolleistenimages, ein Bild laden und legen die transparente Farbe des Bilds festlegen.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#32](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#32)]  
[!CODE [NVC_MFC_VisualStudioDemo#33](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#33)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md)  
  
## Anforderungen  
 **Header:** afxtoolbarimages.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)