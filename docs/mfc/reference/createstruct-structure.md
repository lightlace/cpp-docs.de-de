---
title: "CREATESTRUCT-Struktur"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CREATESTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CREATESTRUCT-Struktur"
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CREATESTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CREATESTRUCT`\-Struktur definiert, die Initialisierungsparameter die der Fensterprozedur eine Anwendung übergeben werden.  
  
## Syntax  
  
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
  
#### Parameter  
 `lpCreateParams`  
 Punkte, um das Fenster zu erstellen zu den zu verwendenden Daten.  
  
 `hInstance`  
 Identifiziert das ModulInstanzhandle des Moduls, dem das neue Fenster besitzt.  
  
 `hMenu`  
 Identifiziert das durch das neue Fenster verwendet werden, Menü.  Wenn ein untergeordnetes Fenster, die ganzzahlige ID enthält  
  
 `hwndParent`  
 Identifiziert das Fenster, das das neue Fenster besitzt.  Dieser Member ist **NULL**, wenn das neue Fenster ein Fenster der obersten Ebene ist.  
  
 `cy`  
 Gibt die Höhe des neuen Fensters an.  
  
 `cx`  
 Gibt die Breite des neuen Fensters an.  
  
 `y`  
 Gibt der y\-Koordinate der linken oberen Ecke des neuen Fensters an.  Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster ein untergeordnetes Fenster ist; andernfalls sind Koordinaten relativ zum Bildschirmursprung.  
  
 `x`  
 Gibt der x\-Koordinate der linken oberen Ecke des neuen Fensters an.  Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster ein untergeordnetes Fenster ist; andernfalls sind Koordinaten relativ zum Bildschirmursprung.  
  
 `style`  
 Gibt [Format](../../mfc/reference/styles-used-by-mfc.md) des neuen Fensters an.  
  
 `lpszName`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Namen des neuen Fensters angibt.  
  
 `lpszClass`  
 Zeigt auf eine auf NULL endende Zeichenfolge, die den Windows\-Klassennamen des neuen Fensters angibt \(Struktur einer [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) ; Weitere Informationen finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 `dwExStyle`  
 [erweitertes Format](../../mfc/reference/extended-window-styles.md) Gibt für das neue Fenster an.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../Topic/CWnd::OnCreate.md)