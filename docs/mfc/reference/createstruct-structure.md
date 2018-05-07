---
title: CREATESTRUCT-Struktur | Microsoft Docs
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
ms.openlocfilehash: e51aed1eb7f74c721a5a4da092f205a2492ba5f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 `lpCreateParams`  
 Zeigt auf Daten verwendet werden, um das Fenster zu erstellen.  
  
 `hInstance`  
 Identifiziert das Modul Instanzhandle des Moduls, das das neue Fenster besitzt.  
  
 `hMenu`  
 Identifiziert das Menü im neuen Fenster verwendet werden. Wenn ein untergeordnetes Fenster enthält die Integer-ID.  
  
 `hwndParent`  
 Identifiziert das Fenster, das das neue Fenster besitzt. Bei diesem Member handelt **NULL** , wenn das neue Fenster der obersten Ebene ist.  
  
 `cy`  
 Gibt die Höhe des neuen Fensters an.  
  
 `cx`  
 Gibt die Breite des neuen Fensters an.  
  
 `y`  
 Gibt die y-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fensters angezeigt, wenn das neue Fenster ein untergeordnetes Fenster ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.  
  
 `x`  
 Gibt die X-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fensters angezeigt, wenn das neue Fenster ein untergeordnetes Fenster ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.  
  
 `style`  
 Gibt an, des neuen Fensters [Stil](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die das neue Fenster Namen angibt.  
  
 `lpszClass`  
 Verweist auf eine auf Null endende Zeichenfolge, die das neue Fenster Windows-Klassennamen angibt (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur; Weitere Informationen finden Sie im Windows SDK).  
  
 `dwExStyle`  
 Gibt an, die [erweiterter Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) für das neue Fenster.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


