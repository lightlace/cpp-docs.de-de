---
title: "CD2DBitmap-Klasse"
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
  - "afxrendertarget/CD2DBitmap"
  - "CD2DBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmap-Klasse"
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DBitmap-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1Bitmap".  
  
## Syntax  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Überladen.  Erstellt ein CD2DBitmap\-Objekt von HBITMAP.|  
|[CD2DBitmap::~CD2DBitmap](../Topic/CD2DBitmap::~CD2DBitmap.md)|Der Destruktor.  Aufgerufen, wenn ein D2D\-Bitmapobjekt zerstört wird.|  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Überladen.  Erstellt ein CD2DBitmap\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::Attach](../Topic/CD2DBitmap::Attach.md)|Fügt vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DBitmap::CopyFromBitmap](../Topic/CD2DBitmap::CopyFromBitmap.md)|Kopiert den angegebenen Bereich aus der angegebenen Bitmap in die aktuelle Bitmap|  
|[CD2DBitmap::CopyFromMemory](../Topic/CD2DBitmap::CopyFromMemory.md)|Kopiert den angegebenen Bereich vom Arbeitsspeicher in die aktuelle Bitmap|  
|[CD2DBitmap::CopyFromRenderTarget](../Topic/CD2DBitmap::CopyFromRenderTarget.md)|Kopiert den angegebenen Bereich aus dem angegebenen Renderingziel in die aktuelle Bitmap|  
|[CD2DBitmap::Create](../Topic/CD2DBitmap::Create.md)|Erstellt ein CD2DBitmap.  \(Überschreibungen [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmap::Destroy](../Topic/CD2DBitmap::Destroy.md)|Zerstört ein CD2DBitmap\-Objekt.  \(Überschreibungen [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBitmap::Detach](../Topic/CD2DBitmap::Detach.md)|Trennt Ressourcenschnittstelle vom Objekt|  
|[CD2DBitmap::Get](../Topic/CD2DBitmap::Get.md)|Schnittstelle der EINGABETASTE ID2D1Bitmap|  
|[CD2DBitmap::GetDPI](../Topic/CD2DBitmap::GetDPI.md)|Geben Sie die DPI \(Dots Per Inch\) der Bitmap zurück|  
|[CD2DBitmap::GetPixelFormat](../Topic/CD2DBitmap::GetPixelFormat.md)|Ruft das Pixelformat und den Alphamodus der Bitmap ab|  
|[CD2DBitmap::GetPixelSize](../Topic/CD2DBitmap::GetPixelSize.md)|Gibt die Größe, in den geräteabhängigen Einheiten \(Pixel\), der Bitmap zurück|  
|[CD2DBitmap::GetSize](../Topic/CD2DBitmap::GetSize.md)|Gibt die Größe, in den geräteunabhängige Pixel \(Bäder\), der Bitmap zurück|  
|[CD2DBitmap::IsValid](../Topic/CD2DBitmap::IsValid.md)|Überprüfungsressourcengültigkeit \(Überschreibungen [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::CommonInit](../Topic/CD2DBitmap::CommonInit.md)|Initialisiert das Objekt|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::operator ID2D1Bitmap\*](../Topic/CD2DBitmap::operator%20ID2D1Bitmap*.md)|Schnittstelle der EINGABETASTE ID2D1Bitmap|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBitmap::m\_bAutoDestroyHBMP](../Topic/CD2DBitmap::m_bAutoDestroyHBMP.md)|TRUE, wenn m\_hBmpSrc zerstört wird; andernfalls FALSE.|  
|[CD2DBitmap::m\_hBmpSrc](../Topic/CD2DBitmap::m_hBmpSrc.md)|Quellbitmaphandle.|  
|[CD2DBitmap::m\_lpszType](../Topic/CD2DBitmap::m_lpszType.md)|Ressourcentyp.|  
|[CD2DBitmap::m\_pBitmap](../Topic/CD2DBitmap::m_pBitmap.md)|Speichert einen Zeiger auf einen ID2D1Bitmap\-Objekt.|  
|[CD2DBitmap::m\_sizeDest](../Topic/CD2DBitmap::m_sizeDest.md)|Bit\-Übersichtszielgröße.|  
|[CD2DBitmap::m\_strPath](../Topic/CD2DBitmap::m_strPath.md)|Botmap\-Dateipfad.|  
|[CD2DBitmap::m\_uiResID](../Topic/CD2DBitmap::m_uiResID.md)|Bitmapressource ID|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBitmap](../../mfc/reference/cd2dbitmap-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)