---
title: BITMAPINFO-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9b1bd896157d7f11792a5a6514e30ecd3d46a19
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336256"
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO-Struktur
Die `BITMAPINFO`-Struktur definiert die Abmessungen und die Farbinformationen für eine geräteunabhängige Bitmap (DIB) von Windows.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>Parameter  
 *bmiHeader*  
 Gibt an, eine [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) -Struktur, die Informationen über die Dimensionen und das farbenformat einer geräteunabhängigen Bitmap enthält.  
  
 *bmiColors*  
 Gibt ein Array von [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) oder DWORD-Datentypen, die die Farben in der Bitmap definieren.  
  
## <a name="remarks"></a>Hinweise  
 Eine geräteunabhängige Bitmap besteht aus zwei verschiedenen Teilen: einer `BITMAPINFO`-Struktur, die die Abmessungen und Farben der Bitmap beschreibt, und einem Bytearray, das die Pixel in der Bitmap angibt. Die Bits im Array werden zusammengefasst, aber jede Scanzeile muss werden mit Nullen aufgefüllt am endet eine **lange** Grenze. Wenn die Höhe positiv ist, ist der Ursprung der Bitmap die linke untere Ecke. Ist die Höhe negativ, ist der Ursprung die linke obere Ecke.  
  
 Ein *gepackte Bitmap* ist eine Bitmap, in dem das Bytearray unmittelbar folgt, die `BITMAPINFO` Struktur. Auf gepackte Bitmaps wird von einem einzelnen Zeiger verwiesen.  
  
 Weitere Informationen zu den `BITMAPINFO` -Struktur und die entsprechenden Werte für Mitglieder der `BITMAPINFOHEADER` und `RGBQUAD` Strukturen finden Sie unter den folgenden Themen in der Windows SDK-Dokumentation.  
  
- [BITMAPINFO-Struktur](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) Struktur  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) Struktur  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

