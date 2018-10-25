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
ms.openlocfilehash: db41deda6040121e3d74958f4616a1f3364f6f23
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064809"
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

*lpCreateParams*<br/>
Verweist auf Daten, die zum Erstellen des Fensters verwendet werden.

*hInstance*<br/>
Gibt das Modul Instanzhandle des Moduls, das das neue Fenster besitzt.

*hMenu*<br/>
Identifiziert das Menü im neuen Fenster verwendet werden. Wenn ein untergeordnetes Fenster, enthält die ganzzahlige ID

*hwndParent*<br/>
Gibt das Fenster, das das neue Fenster besitzt. Dieser Member ist NULL, wenn das neue Fenster der obersten Ebene ist.

*CY*<br/>
Gibt die Höhe des neuen Fensters.

*CX*<br/>
Gibt die Breite des neuen Fensters.

*y*<br/>
Gibt die y-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster eines untergeordneten Fensters ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.

*w*<br/>
Gibt die X-Koordinate der oberen linken Ecke des neuen Fensters an. Koordinaten sind relativ zum übergeordneten Fenster, wenn das neue Fenster eines untergeordneten Fensters ist; Andernfalls sind Koordinaten relativ zum Bildschirmursprung ein.

*Stil*<br/>
Gibt an, die im neuen Fensters [Stil](../../mfc/reference/styles-used-by-mfc.md).

*Wert*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die das neue Fenster Namen angibt.

*lpszClass*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die Windows-Klassennamen des neuen Fensters angibt (eine [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur; Weitere Informationen finden Sie im Windows SDK).

*dwExStyle*<br/>
Gibt an, die [erweiterten Stil](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) für das neue Fenster.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)

