---
title: CREATESTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6036490b21ccbd86dfed56ea90226cbb2db8d596
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848469"
---
# <a name="createstruct-structure"></a>CREATESTRUCT-Struktur
Die `CREATESTRUCT` Struktur definiert die Initialisierungsparameter an die Fensterprozedur einer Anwendung übergeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *lpCreateParams*  
 Verweist auf Daten, die zum Erstellen des Fensters verwendet werden.  
  
 *hInstance*  
 Gibt das Modul Instanzhandle des Moduls, das das neue Fenster besitzt.  
  
 *hMenu*  
 Identifiziert das Menü im neuen Fenster verwendet werden. Wenn ein untergeordnetes Fenster, enthält die ganzzahlige ID  
  
 *hwndParent*  
 Gibt das Fenster, das das neue Fenster besitzt. Dieser Member ist NULL, wenn das neue Fenster der obersten Ebene ist.  
  
 *CY*  
 Gibt die Höhe des neuen Fensters.  
  
 *CX*  
 Gibt die Breite des neuen Fensters.  
  
 *y*  
 Gibt die y-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster eines untergeordneten Fensters ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.  
  
 *w*  
 Gibt die X-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster eines untergeordneten Fensters ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.  
  
 *Stil*  
 Gibt an, die im neuen Fensters [Stil](../../mfc/reference/styles-used-by-mfc.md).  
  
 *Wert*  
 Verweist auf eine auf Null endende Zeichenfolge, die das neue Fenster Namen angibt.  
  
 *lpszClass*  
 Verweist auf eine auf Null endende Zeichenfolge, die Windows-Klassennamen des neuen Fensters angibt (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur; Weitere Informationen finden Sie im Windows SDK).  
  
 *dwExStyle*  
 Gibt an, die [erweiterten Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) für das neue Fenster.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


