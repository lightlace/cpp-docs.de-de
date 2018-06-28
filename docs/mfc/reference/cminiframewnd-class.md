---
title: CMiniFrameWnd Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 766faaa50e4efead96ff72c67aee71fec2386b18
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038582"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd-Klasse
Stellt ein Rahmenfenster mit halber Höhe dar, das in der Regel um unverankerte Symbolleisten sichtbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Erstellt ein `CMiniFrameWnd`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|Erstellt eine `CMiniFrameWnd` Objekt nach der Erstellung.|  
|[CMiniFrameWnd::CreateEx](#createex)|Erstellt eine `CMiniFrameWnd` Objekt (mit zusätzlichen Optionen) nach der Erstellung.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Minirahmenfenster Verhalten sich wie normale Rahmenfenstern werden, außer dass sie verfügen nicht über die Schaltflächen maximieren/minimieren oder Menüs und Sie nur auf dem Systemmenü zu schließen, sie klicken müssen.  
  
 Verwenden einer `CMiniFrameWnd` Objekt, definieren Sie zunächst das Objekt. Rufen Sie anschließend die [erstellen](#create) Memberfunktion versucht, das Minirahmenfenster angezeigt.  
  
 Weitere Informationen zur Verwendung von `CMiniFrameWnd` Objekte finden Sie im Artikel [andockbare und unverankerte Symbolleisten](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd  
 Erstellt eine `CMiniFrameWnd` -Objekt, aber das Fenster nicht erstellt.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Erstellen des Fensters [CMiniFrameWnd::Create](#create).  
  
##  <a name="create"></a>  CMiniFrameWnd::Create  
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
 *lpClassName*  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Namen die Windows-Klasse. Der Klassenname kann einen beliebigen Namen, die mit dem globalen registriert sein [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) Funktion. Wenn **NULL**, Window-Klasse wird vom Framework für Sie registriert werden. MFC bietet der Standardklasse, die folgenden Formate und Attribute:  
  
-   Legt formatieren Bit **CS_DBLCLKS**, sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maustaste doppelklickt.  
  
-   Legt formatieren Bits **CS_HREDRAW** und **CS_VREDRAW**, die direkt den Inhalt des Clientbereichs neu gezeichnet wird, wenn das Fenster Größe ändert.  
  
-   Setzt den Cursor für die Klasse auf der Windows-Standard **IDC_ARROW**.  
  
-   Wird von der Klasse Hintergrundpinsel auf **NULL**, damit das Fenster des Hintergrunds nicht gelöscht werden.  
  
-   Legt das Symbol "Klasse" auf die standardmäßigen, Winkende Flag Windows Logo-Symbol fest.  
  
-   Das Fenster festgelegt an Standardeinstellung Größe und Position, wie von Windows angegeben.  
  
 *lpWindowName*  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen enthält.  
  
 *dwStyle*  
 Gibt an, die Fenster-Stilattribute. Diese können standard Fensterstile und mindestens eine der folgenden Sonderzeichen enthalten:  
  
- **MFS_MOVEFRAME** ermöglicht das Minirahmenfenster verschoben werden soll, indem Sie auf keinem Rand des Fensters, nicht nur die Beschriftung.  
  
- **MFS_4THICKFRAME** Größenänderung des Minirahmenfenster deaktiviert.  
  
- **MFS_SYNCACTIVE** synchronisiert die Aktivierung das Minirahmenfenster an die Aktivierung des übergeordneten Fensters.  
  
- **MFS_THICKFRAME** ermöglicht das Minirahmenfenster zu klein können den Inhalt des Clientbereichs.  
  
- **MFS_BLOCKSYSMENU** deaktiviert den Zugriff auf das Systemmenü und dem Steuerelementmenü und konvertiert diese in Teil der Beschriftung (Titelleiste).  
  
 Finden Sie unter [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Fensterstilwerte. Ist die typische Kombination Minirahmenfenster zum **WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU**.  
  
 *Rect*  
 Ein `RECT` Struktur, die die gewünschten Dimensionen des Fensters angibt.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Fenster. Verwendung **NULL** für Fenster auf oberster Ebene.  
  
 *nID*  
 Wenn das Minirahmenfenster als untergeordnetes Fenster erstellt wird, ist dies der Bezeichner des untergeordneten Steuerelements. andernfalls 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** Klassennamen und entweder ist der Name des Fensters initialisiert und Standardwerte für die Rahmenart und die übergeordnete registriert.  
  
##  <a name="createex"></a>  CMiniFrameWnd::CreateEx  
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
 *dwExStyle*  
 Gibt den erweiterten Stil des der `CMiniFrameWnd` erstellt wird. Wendet keine der der [erweiterten Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) an das Fenster.  
  
 *lpClassName*  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Namen die Windows-Klasse (eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur). Der Klassenname kann einen beliebigen Namen, die mit dem globalen registriert sein [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) Funktion oder einem der vordefinierten Steuerelementklasse Namen. Es muss nicht **NULL**.  
  
 *lpWindowName*  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen enthält.  
  
 *dwStyle*  
 Gibt an, die Fenster-Stilattribute. Finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) eine Beschreibung der möglichen Werte.  
  
 *Rect*  
 Die Größe und Position des Fensters, in Clientkoordinaten der *pParentWnd*.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Fenster-Objekt.  
  
 *nID*  
 Der Bezeichner des untergeordneten Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Die `CreateEx` Parameter geben die **WNDCLASS**, Stil des Fensters, und (optional) ursprüngliche Position und Größe des Fensters. `CreateEx` gibt auch an des Fensters übergeordnete (sofern vorhanden) und -ID.  
  
 Wenn `CreateEx` ausgeführt wird, sendet Windows die [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) Meldungen an das Fenster.  
  
 Um die Standard-Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CMiniFrameWnd`, eine meldungszuordnung an die neue Klasse hinzufügen und Memberfunktionen für die oben genannten Nachrichten bereitstellen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Weitere überschreiben **auf *** Nachricht* message-Handler können Sie weitere Funktionen in der abgeleiteten Klasse hinzufügen.  
  
 Wenn die **WS_VISIBLE** Stil angegeben ist, sendet Windows die Fenster alle Nachrichten, die für die Aktivierung und die Fenster anzeigen. Der Fensterstil eine Titelleiste an, der Fenstertitel verweist, zu der *LpszWindowName* Parameter in der Titelleiste angezeigt wird.  
  
 Die *DwStyle* Parameter kann eine beliebige Kombination von [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 Die alten Stil Palette Toolbox-Fenster werden nicht mehr unterstützt. Das alte Format, eine Schaltfläche "X" schließen keine, wurde unterstützt, wenn eine MFC-Anwendung unter älteren Versionen von Windows ausgeführt, aber nicht mehr in Visual c++.NET unterstützt wird. Nur das neue `WS_EX_TOOLWINDOW` Stil wird jetzt unterstützt; eine Beschreibung dieses Formats, finden Sie unter [erweiterten Fensterstile](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
## <a name="see-also"></a>Siehe auch  
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
