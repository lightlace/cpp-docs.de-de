---
title: "BITMAPINFO-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAPINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAPINFO-Struktur"
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# BITMAPINFO-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `BITMAPINFO`\-Struktur definiert die Abmessungen und die Farbinformationen für eine geräteunabhängige Bitmap \(DIB\) von Windows.  
  
## Syntax  
  
```  
typedef struct tagBITMAPINFO {  
   BITMAPINFOHEADER bmiHeader;  
   RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### Parameter  
 `bmiHeader`  
 Gibt eine [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)\-Struktur an, die Informationen über die Abmessungen und das Farbenformat einer geräteunabhängigen Bitmap enthält.  
  
 `bmiColors`  
 Gibt ein Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)\- oder `DWORD`\-Datentypen an, die die Farben in der Bitmap definieren.  
  
## Hinweise  
 Eine geräteunabhängige Bitmap besteht aus zwei verschiedenen Teilen: einer `BITMAPINFO`\-Struktur, die die Abmessungen und Farben der Bitmap beschreibt, und einem Bytearray, das die Pixel in der Bitmap angibt.  Die Bits im Array werden zusammengefasst, jede Scanzeile muss jedoch mit Nullen aufgefüllt werden, um an einer `LONG`\-Grenze zu enden.  Wenn die Höhe positiv ist, ist der Ursprung der Bitmap die linke untere Ecke.  Ist die Höhe negativ, ist der Ursprung die linke obere Ecke.  
  
 Eine *gepackte Bitmap* ist eine Bitmap, bei der das Bytearray unmittelbar auf die `BITMAPINFO`\-Struktur folgt.  Auf gepackte Bitmaps wird von einem einzelnen Zeiger verwiesen.  
  
 Weitere Informationen über die `BITMAPINFO`\-Struktur und die entsprechenden Werte für Member der `BITMAPINFOHEADER`\- und `RGBQUAD`\-Struktur finden Sie in den folgenden Themen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\-Dokumentation.  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="b5dd2e8c9cedbac12eb858bd01a029a2" class\="tgtSentence"\>BITMAPINFO\-Struktur\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
-   [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)\-Struktur  
  
-   [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)\-Struktur  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)