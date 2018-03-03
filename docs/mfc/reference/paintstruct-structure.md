---
title: PAINTSTRUCT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92583bba3dca60caa2895966a87571dc60805475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT-Struktur
Die `PAINTSTRUCT` Struktur enthält Informationen, die verwendet werden kann, das den Clientbereich eines Fensters gezeichnet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *hdc*  
 Identifiziert den Anzeigekontext für Paint-Ereignisse verwendet werden soll.  
  
 *fErase*  
 Gibt an, ob der im Hintergrund neu gezeichnet werden muss. Es ist nicht 0, wenn die Anwendung neu Hintergrund gezeichnet werden soll. Die Anwendung ist verantwortlich für den Hintergrund zeichnen, wenn eine Windows-Fensterklasse ohne Hintergrundpinsel erstellt wird (siehe dazu die Beschreibung der **HbrBackground** Mitglied der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur im Windows SDK).  
  
 *rcPaint*  
 Gibt an, der oberen linken und unteren linken Ecke des Rechtecks, in dem das Zeichnen angefordert wird.  
  
 *fRestore*  
 Reservierten Member. Sie wird intern von Windows verwendet.  
  
 *fIncUpdate*  
 Reservierten Member. Sie wird intern von Windows verwendet.  
  
 *RgbReserved [16]*  
 Reservierten Member. Eine reservierte Speicherblock, der intern von Windows verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

