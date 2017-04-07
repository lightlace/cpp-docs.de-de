---
title: CMiniFrameWnd Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd class
- mini-frame windows
- toolbars [C++]
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1229f5405c9eeb90abcdc54108ed26e28d94f0e0
ms.lasthandoff: 02/24/2017

---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd-Klasse
Stellt ein Rahmenfenster mit halber Höhe dar, das in der Regel um unverankerte Symbolleisten sichtbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Erstellt ein `CMiniFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|Erstellt ein `CMiniFrameWnd` Objekt nach der Erstellung.|  
|[CMiniFrameWnd::CreateEx](#createex)|Erstellt ein `CMiniFrameWnd` Objekt (mit weiteren Optionen) nach der Erstellung.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Minirahmenfenster Verhalten sich wie normale Rahmenfenster, außer dass sie verfügen nicht über die Schaltflächen maximieren/minimieren oder Menüs und Sie nur ein-Klick auf das Systemmenü, um diese zu schließen müssen.  
  
 Verwenden einer `CMiniFrameWnd` Objekt, das Objekt zuerst definieren. Rufen Sie dann die [erstellen](#create) Memberfunktion Minirahmenfenster angezeigt.  
  
 Weitere Informationen zur Verwendung von `CMiniFrameWnd` Objekte finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 Erstellt ein `CMiniFrameWnd` Objekt, aber das Fenster nicht erstellt.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Erstellen des Fensters [CMiniFrameWnd::Create](#create).  
  
##  <a name="create"></a>CMiniFrameWnd::Create  
 Erstellt die Windows-Minirahmenfenster und fügt es der `CMiniFrameWnd` Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpClassName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Windows-Klasse bezeichnet. Der Name der Klasse kann einen beliebigen Namen, die mit dem globalen registriert [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) Funktion. Wenn **NULL**, Window-Klasse wird vom Framework für Sie registriert werden. MFC bietet der Standardklasse, die folgenden Stile und Attribute:  
  
-   Legt Stil Bit **CS_DBLCLKS**, welche sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maus doppelklickt.  
  
-   Legt Stil Bits **CS_HREDRAW** und **CS_VREDRAW**, die direkt den Inhalt des Clientbereichs neu gezeichnet wird, wenn die Größe des Fensters geändert wird.  
  
-   Setzt den Cursor für die Klasse auf dem Windows-Standard **IDC_ARROW**.  
  
-   Wird von der Klasse Hintergrundpinsel auf **NULL**, sodass das Fenster den Hintergrund nicht gelöscht werden.  
  
-   Legt das Symbol "Klasse" standard "," Winkende-Flag Windows Logo-Symbol fest.  
  
-   Das Fenster festgelegt in der Standardgröße und der Position, wie durch Windows.  
  
 `lpWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters enthält.  
  
 `dwStyle`  
 Gibt die Stilattribute Fenster an. Dazu können standard-Window-Stile und mindestens eine der folgenden speziellen gehören:  
  
- **MFS_MOVEFRAME** ermöglicht das Minirahmenfenster verschoben werden soll, indem Sie auf einen beliebigen Rand des Fensters, nicht nur die Überschrift.  
  
- **MFS_4THICKFRAME** Ändern der Größe des Minirahmenfenster deaktiviert.  
  
- **MFS_SYNCACTIVE** synchronisiert die Aktivierung der Minirahmenfenster mit der Aktivierung des übergeordneten Fensters.  
  
- **MFS_THICKFRAME** ermöglicht das Minirahmenfenster kleine wie der Inhalt des Clientbereichs kann geändert werden.  
  
- **MFS_BLOCKSYSMENU** deaktiviert den Zugriff auf das Systemmenü und das Systemmenü und konvertiert sie in Teil der Beschriftung (Titelleiste).  
  
 Finden Sie unter [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Fensterstilwerte. Ist der Standard für Minirahmenfenster verwendete Kombination von **WS_POPUP | WS_CAPTION | WS_SYSMENU**.  
  
 `rect`  
 Ein `RECT` -Struktur, die die gewünschten Dimensionen des Fensters angibt.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster. Verwendung **NULL** für Fenster der obersten Ebene.  
  
 `nID`  
 Wenn das Minirahmenfenster als untergeordnetes Fenster erstellt wird, ist dies die ID des untergeordneten Steuerelements. andernfalls 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** initialisiert Klassennamen und den Namen des Fensters und Standardwerte für die Rahmenart und die übergeordnete registriert.  
  
##  <a name="createex"></a>CMiniFrameWnd::CreateEx  
 Erstellt ein `CMiniFrameWnd`-Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil, der die `CMiniFrameWnd` erstellt wird. Übernehmen Sie alle von der [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md) in das Fenster.  
  
 `lpClassName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die die Windows-Klassennamen (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur). Der Klassenname kann einen beliebigen Namen, die mit dem globalen registriert [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) Funktion oder die Namen der vordefinierten Control-Klasse. Er darf nicht sein **NULL**.  
  
 `lpWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters enthält.  
  
 `dwStyle`  
 Gibt die Stilattribute Fenster an. Finden Sie unter [Fensterstile](../../mfc/reference/window-styles.md) und [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Werte.  
  
 `rect`  
 Die Größe und Position des Fensters, in Clientkoordinaten des `pParentWnd`.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster-Objekt.  
  
 `nID`  
 Der Bezeichner des untergeordneten Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Die `CreateEx` Parameter geben die **WNDCLASS**, Fensterstil und (optional) ursprüngliche Position und Größe des Fensters. `CreateEx`Darüber hinaus gibt des Fensters übergeordnete (sofern vorhanden) und -ID.  
  
 Wenn `CreateEx` ausgeführt wird, sendet Windows die [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) Nachrichten an das Fenster.  
  
 Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CMiniFrameWnd`, Hinzufügen einer Nachricht Zuordnung zu der neuen Klasse und Member-Funktionen für die oben genannten Nachrichten bereitstellen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Überschreiben Sie weitere **auf***Message* message-Handler in der abgeleiteten Klasse weitere Funktionen hinzufügen.  
  
 Wenn die **WS_VISIBLE** Stil angegeben, Windows Fenster sendet alle Nachrichten, die für die Aktivierung und das Fenster anzuzeigen. Wenn der Fensterstil eine Titelleiste angibt, der Titel des Fensters zeigt die `lpszWindowName` Parameter wird in der Titelleiste angezeigt.  
  
 Die `dwStyle` Parameter kann eine beliebige Kombination von [Fensterstile](../../mfc/reference/window-styles.md).  
  
 Die alten Stil Palette Toolbox-Fenster werden nicht mehr unterstützt. Das alte Format, der eine Schaltfläche zum Schließen "X", wurde beim Ausführen einer MFC-Anwendung auf früheren Versionen von Windows, unterstützt jedoch nicht mehr in Visual c++.NET unterstützt wird. Nur die neue `WS_EX_TOOLWINDOW` Stil wird jetzt unterstützt, eine Beschreibung dieses Stils, unter [erweiterte Fensterstile](../../mfc/reference/extended-window-styles.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)

