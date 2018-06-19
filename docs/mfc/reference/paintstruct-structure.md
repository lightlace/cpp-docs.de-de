---
title: PAINTSTRUCT-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfeddfd1ebf0c5c2247b27a0c69a8a6ef33e7766
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370437"
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

