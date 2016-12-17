---
title: "CBitmap Class"
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
  - "CBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmap class"
  - "drawing, Tools"
  - "GDI bitmap"
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt eine Bitmap des Windows GDI \(Graphics Device Interface\) und bietet Memberfunktionen bereit, um die Bitmap zu bearbeiten.  
  
## Syntax  
  
```  
class CBitmap : public CGdiObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBitmap::CBitmap](../Topic/CBitmap::CBitmap.md)|Erstellt ein `CBitmap`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBitmap::CreateBitmap](../Topic/CBitmap::CreateBitmap.md)|Initialisiert das Objekt mit einer geräteabhängigen Speicherbitmap, die eine angegebene Breite, eine Höhe und ein Bitmuster verfügt.|  
|[CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)|Initialisiert das Objekt mit einer Bitmap mit der Breite, Höhe der, und dem Bitmuster \(falls vorhanden\), angegeben in einer **BITMAP**\-Struktur.|  
|[CBitmap::CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)|Initialisiert das Objekt mit einer Bitmap, sodass sie mit einem bestimmten Gerät kompatibel ist.|  
|[CBitmap::CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md)|Initialisiert das Objekt mit einer discardable Bitmap, die mit einem angegebenen Gerät kompatibel ist.|  
|[CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)|Gibt einen Zeiger auf ein `CBitmap`\-Objekt zurück, wenn Sie ein Handle für eine Bitmap Windows `HBITMAP` angegeben werden.|  
|[CBitmap::GetBitmap](../Topic/CBitmap::GetBitmap.md)|Füllt eine **BITMAP**\-Struktur mit Informationen über die Bitmap aus.|  
|[CBitmap::GetBitmapBits](../Topic/CBitmap::GetBitmapBits.md)|Kopiert die Bits der angegebenen Bitmaps in den angegebenen Puffer.|  
|[CBitmap::GetBitmapDimension](../Topic/CBitmap::GetBitmapDimension.md)|Gibt die Breite und Höhe der Bitmaps zurück.  Die Höhe und Breite angenommen werden, durch die [SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)\-Memberfunktion zuvor festgelegt worden zu sein.|  
|[CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md)|Initialisiert das Objekt durch das Laden einer benannten Bitmapressource der ausführbaren Datei der Anwendung und das Anfügen der Bitmap in das Objekt.|  
|[CBitmap::LoadMappedBitmap](../Topic/CBitmap::LoadMappedBitmap.md)|Lädt eine Bitmap und ordnet Farben zu aktuellen Systemfarben zu.|  
|[CBitmap::LoadOEMBitmap](../Topic/CBitmap::LoadOEMBitmap.md)|Initialisiert das Objekt durch das Laden einer vordefinierten Windows\-Bitmaps und das Anfügen der Bitmap in das Objekt.|  
|[CBitmap::SetBitmapBits](../Topic/CBitmap::SetBitmapBits.md)|Legt die Bits einer Bitmap auf den angegebenen Bitwerten fest.|  
|[CBitmap::SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)|Weist einer Breite und Höhe in eine Bitmap im 0,1 \-Millimeter\-Einheiten zu.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBitmap::operator HBITMAP](../Topic/CBitmap::operator%20HBITMAP.md)|Gibt das Windows\-Handles zurück, das dem `CBitmap`\-Objekt angefügt wird.|  
  
## Hinweise  
 Um ein `CBitmap`\-Objekt zu verwenden, erstellen Sie das Objekt, fügen Sie ein Bit\-Übersichtshandle mit einer der Initialisierungsmemberfunktionen an, und rufen Sie dann die Memberfunktionen des Objekts auf.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten wie Sie `CBitmap`, finden [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel\-MDI](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)