---
title: CREATESTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ec72d4725cb7e5959369b24a6ff7f0e3e9da1ca7
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 Identifiziert die Modulinstanz Handle des Moduls, das das neue Fenster besitzt.  
  
 `hMenu`  
 Identifiziert das Menü im neuen Fenster verwendet werden. Wenn ein untergeordnetes Fenster enthält die Integer-ID.  
  
 `hwndParent`  
 Identifiziert das Fenster, das neue Fenster besitzt. Dieser Member ist **NULL** , wenn das neue Fenster der obersten Ebene ist.  
  
 `cy`  
 Gibt die Höhe des neuen Fensters.  
  
 `cx`  
 Gibt die Breite des neuen Fensters.  
  
 `y`  
 Gibt die y-Koordinate der oberen linken Ecke des neuen Fensters. Koordinaten sind relativ zum übergeordneten Fenster, das neue Fenster ist ein untergeordnetes Fenster. Andernfalls werden Koordinaten relativ zum Bildschirmursprung.  
  
 `x`  
 Gibt die X-Koordinate der oberen linken Ecke des neuen Fensters. Koordinaten sind relativ zum übergeordneten Fenster, das neue Fenster ist ein untergeordnetes Fenster. Andernfalls werden Koordinaten relativ zum Bildschirmursprung.  
  
 `style`  
 Gibt des neuen Fensters [Stil](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die das neue Fenster Namen angibt.  
  
 `lpszClass`  
 Verweist auf eine auf Null endende Zeichenfolge, die das neue Fenster Windows-Klassennamen angibt (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur; Weitere Informationen finden Sie unter den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
 `dwExStyle`  
 Gibt die [erweiterten Stil](../../mfc/reference/extended-window-styles.md) für das neue Fenster.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



